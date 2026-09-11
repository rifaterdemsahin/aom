# ☁️ Azure Key Vault & Credentials Setup Guide

> **Stage 2: Environment** — Configuration and onboarding instructions for secrets management.

This project **reuses** the delivery-pilot Key Vault. Do **not** create a new vault.

| Item | Value |
|------|--------|
| Vault | `dp-kv-deliverypilot` |
| Secrets path | `/vaults/dp-kv-deliverypilot/secrets` |
| Local name | `AZURE_KEYVAULT_NAME` in `.env.example` |

---

## 🔒 Azure Key Vault Setup

All environment variables and secrets must be loaded dynamically from Azure Key Vault at runtime. Never commit values.

### 1. Azure Authentication
```bash
az login
az account set --subscription "your-subscription-name-or-id"
az keyvault show --name dp-kv-deliverypilot
```

### 2. Do not provision a new Key Vault

The vault already exists. Skip `az group create` / `az keyvault create`. If `az keyvault show` fails, fix RBAC on the existing vault — do not invent `aom-kv` or another name.

### 3. Registering secrets (existing vault)

```bash
az keyvault secret set --vault-name dp-kv-deliverypilot --name "FLY-API-TOKEN" --value "<from-fly>"
az keyvault secret set --vault-name dp-kv-deliverypilot --name "CLOUDFLARE-API-TOKEN" --value "<from-cloudflare>"
az keyvault secret set --vault-name dp-kv-deliverypilot --name "AZURE-STORAGE-CONNECTION-STRING" --value "<project-storage>"
az keyvault secret list --vault-name dp-kv-deliverypilot --query "[].name" -o tsv
```

Load at runtime (never print secret values into git):

```bash
az keyvault secret show --vault-name dp-kv-deliverypilot --name "AZURE-STORAGE-CONNECTION-STRING" --query value -o tsv
```

---

## 🔑 GitHub Actions Integration

1. Use an existing service principal with Key Vault Secrets User on `dp-kv-deliverypilot`.
2. Store the JSON as GitHub Repository Secret `AZURE_CREDENTIALS` (repo settings — not this tree).
3. In workflows:
   ```yaml
   - name: Azure Login
     uses: azure/login@v1
     with:
       creds: ${{ secrets.AZURE_CREDENTIALS }}
   - name: Load Key Vault secrets
     uses: Azure/get-keyvault-secrets@v1
     with:
       keyvault: dp-kv-deliverypilot
       secrets: FLY-API-TOKEN, CLOUDFLARE-API-TOKEN, AZURE-STORAGE-CONNECTION-STRING
   ```

This repo is a **static GitHub Pages** frontend (RULE-003). Fly.io / Cloudflare Workers credentials still live in this vault for when a backend is added.

---

## 📁 Azure project-based storage (default)

Default file/blob storage is Azure Storage scoped to this project (RULE-004 / SPEC-012). Connection strings live in `dp-kv-deliverypilot`. Fly volumes, Cloudflare R2, local disk, and git LFS are not the default.

```bash
az keyvault secret set --vault-name dp-kv-deliverypilot --name "AZURE-STORAGE-CONNECTION-STRING" \
  --value "$(az storage account show-connection-string --name <aom-storage-account> --resource-group <existing-rg> -o tsv)"
```

Structured data may still use Supabase.

---

## 🧪 Verification Checklist
- [ ] Azure CLI authenticated
- [ ] `az keyvault show --name dp-kv-deliverypilot` succeeds
- [ ] No new Key Vault was created
- [ ] Zero secret values committed to source files
