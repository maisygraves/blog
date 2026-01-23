# b-Log
a personal knowledge graph and portfolio engine designed to track the evolution of my technical skills through projects and notes.

## 1. System Architecture
The system is currently a static Jekyll site, designed to transition into a database-backed portfolio.

**Current Flow**

Markdown (Front Matter) --> Jekyll + Liquid --> GitHub Pages

**Target Architecture** (planned)
The database acts as a queryable "source of truth" for career analytics, while Jekyll handles the static presentation.

Markdown --> Ingestion Script --> PostgreSQL --> Data Insights/Build Process

## 2. The Data Contract
To ensure future compatibility with the PostgreSQL backend, all content must follow this metadata schema in the YAML front matter:

|Field     |Type  |Requirement|Description                           |
|----------|------|-----------|--------------------------------------|
|category  |enum  |required   |must be exactly 'project' or 'note'   |
|skills    |list  |required   |array of skills (list by Grolemund)   |
|tech stack|list  |required   |array of tools (e.g. Postgres, Python)|
|repo_url  |string|optional   |required if category: project         |

*example front matter:*
```
YAML
---
title: ""
category: project
skills: [data-retrieval, visualization]
techstack: [Python, Postgres]
repo_url: ""
---
```
## 3. Database Design (planned)
The backend is modeled to handle many-to-many relationships between posts and skills/tech stack.

- posts TABLE: core metadata(title, date, url, category)

- skills TABLE: master list of tech stack tools and data science competencies.

- post_skills/post_techstack BRIDGE: links skills and tech stack to post, allowing for queries like 'show all projects where they used Postgres'.

## 4. Features and Requirements

**Content Browsing and Navigation**

- dynamic skills and tech stack pages: each skill/tool has a dedicated page listing all associated projects and notes.

- bi-directional linking: access skill/tech stack post-lists from posts; access posts from skill/tech stack pages.

- curated resources: a dedicated space for references used during project development.

**Technical Practice Goals**

- knowledge graphing: moving beyond 'tags' to a relational understanding of my own work.

- iterative deployment: using modular components and clean documentation best practices for facilitating reproducibility.

- backend integration: practice in schema design, normalization and ETL logic.

## 5. Deployment and Maintenance

**Hosting**

- frontend: GitHub Pages

- backend (planned): local PostgreSQL with future migration to cloud infrastructure.

**Manual Maintenance Workflow**

1. draft: create Markdown file with compliant front matter.

2. verify: ensure all listed skills and tools exist in the master lists to maintain referential integrity.

3. sync (planned): run Python ingestion script to update from PostgreSQL database.

4. deploy: push to GitHub to trigger the Jekyll build.

## 6. Purpose and Audience

- audience: prospective employers, peers and myself

- non-goals: this project is strictly for professional development and knowledge sharing; it is not for monetization.
