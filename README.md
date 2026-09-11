# 🧩 Adaptive Object Model

Live explainer (this repo on GitHub Pages):

**[https://rifaterdemsahin.github.io/aom/](https://rifaterdemsahin.github.io/aom/)**

Open [`index.html`](index.html) for the illustrated version — Type Square diagrams, emojis, and the AI / rclone / multi-model argument.

Inspired by [Joe Yoder](https://joeyoder.com/) and Ralph Johnson: [adaptiveobjectmodel.com](https://adaptiveobjectmodel.com/).

---

## 🧭 The idea

An **Adaptive Object Model (AOM)** represents *classes, attributes, relationships, and behavior as metadata*. The model the user cares about is data. The coded object model is a small **interpreter** of that data.

Yoder’s line:

> The object model that the user cares about is part of the database, and the object model of the code is just an interpreter of the users’ object model.

If you want something to change quickly, you push it into data.

## 🟦 Type Square

Apply **Type Object** twice and **Property** once:

| Type (metadata) | Instance (runtime) |
| --- | --- |
| `EntityType` | `Entity` |
| `PropertyType` | `Property` |

Around that square: Accountability / Entity–Relationship, Strategy, Rule Objects, Builder, Interpreter, editors.

## 🤖 What changes with AI / LLMs

The kernel is still a tiny interpreter. What collapsed is the cost of **creating and revising** the metadata:

- LLMs draft EntityTypes, PropertyTypes, rules, tests, editors, and adapters
- Natural language becomes a usable editor; humans still own invariants
- You generate projections (SQL, graph, vectors, files) instead of freezing one class tree

## 🚚 rclone and moving models

Abstract models used to be stuck in one database. If types are **files** (YAML, JSON, Markdown), [rclone](https://rclone.org/) copies them across local disks, Google Drive, Azure Files, S3, and seventy-plus backends (`copy`, `sync`, `mount`, union/combine).

The interpreter does not care which backend held the YAML.

## 🗂️ Multiple data models

One conceptual AOM, several physical stores:

| Store | Job | AOM mapping |
| --- | --- | --- |
| 📄 Files | Edit, git, rclone | Source of truth for types and rules |
| 🧮 Relational | Integrity, reports | Property values and constraints |
| 🕸️ Graph | Paths and accountability | Entity–Relationship |
| ✨ Vectors | Semantic find / RAG | Embeddings of entities and rules |
| ⚙️ Runtime | Live validation | Yoder’s kernel |

## 🪄 Why the extra abstraction is cheap now

Runtime models used to cost a year of editors and ETL. Now:

1. **Creation** — LLMs draft the meta-model
2. **Motion** — rclone / git move it
3. **Plurality** — graph + vectors + tables + files as projections
4. **Editing** — Markdown and prompts instead of a custom workbench

Keep the kernel small. A sloppy interpreter is still an accidental programming language.

## 📚 Sources

- Yoder & Johnson, *[The Adaptive Object-Model Architectural Style](https://adaptiveobjectmodel.com/WICSA3/ArchitectureOfAOMsWICSA3.htm)* (WICSA 2002)
- Yoder, Johnson et al., *Architecture and Design of Adaptive Object-Models* (2001)
- [adaptiveobjectmodel.com](https://adaptiveobjectmodel.com/)
- [rclone](https://rclone.org/)

## 🔗 This site

| File | Role |
| --- | --- |
| [index.html](index.html) | GitHub Pages homepage |
| [images/](images/) | Concept photographs |
| [README.md](README.md) | This note (linked from the page) |
