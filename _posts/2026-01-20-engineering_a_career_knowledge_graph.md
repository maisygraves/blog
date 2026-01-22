---
title: "I engineered a career knowledge graph like a database"
category: note
skills: [data-storage, data-retrieval, automation, logical-reasoning]
tools: [Linux, HTML, CSS, Git, GitHub, Jekyll, Visual-Studio-Code]
---

Most portfolios summarize projects that then sit in a linear timeline on their website or GitHub. I decided to take a different approach and turn my list of projects into an evolving network of skills, tools and competencies that grow over time.

To achieve this, I designed a queryable portfolio engine, framing my professional development like a data engineering problem. The target goal is to transform a list of projects and technical notes into an evolving knowledge graph.

# The Vision
My goal is to move away from flat-file tagging to a **relational understanding** of skills. Every post is a data input that will adhere to a predefined schema to ensure the portfolio is analytics-ready from day one.

# System Architecture and Migration Path
This project will follow an iterative deployment strategy, moving from static files to a robust relational backend as I grow my capabilities (and indulge my curiosity).

1. Stage One (current) - static ingestion:
Markdown (YAML front matter) --> Jekyll + Liquid --> GitHub Pages

2. Stage Two (local migration) - ETL pipeline
Python Script --> PostgreSQL (local via psql)

3. Stage Three (target state) - relational engine:
PostgreSQL database --> Python engine --> Markdown/YAML interface --> hosted on GitHub Pages

# Data Entities and Relational Logic
To support queries (e.g. "show every project using Python but not SQL"), the database utilizes a normalized, many-to-many architecture.

## The Data Contract

|Entity    |Type     |Requirement                                       |
|----------|---------|--------------------------------------------------|
|Posts     |node     |categorized as either a **project** or a **note** |
|Skills |attribute|maps to 17 skills from the Grolemund/Wickham model|
|Tools|attribute|array of tools (e.g. Postgres)                    |
|Resources |reference|curated list of external artifacts                |

## Relational Mapping
- Bridge tables: **Post_Skills** and **Post_Tools** junction tables enable the networked structure.
- Normalization: **Skills** and **Tools** exist as unique entities to ensure consistency and prevent tag bloat.

# Functional Requirements
- Schema Enforcement: Entries need to follow the YAML front matter "contract".
-Bi-Directional Discovery: Clicking a skill or tool must surface every project and technical note exemplifying that skill or tool.
- Portfolio Filtering: provide a "recruiter view" to filter by specific competencies defined both in the skill framework inspired by Grolemund and Wickham's venn diagram and in my growing "toolbox".

# Non-Functional Requirements
- Data Integrity: GIGO prevention via Jekyll-Liquid templates.
- Iterative Design: Architecture to remain modular,allowing the source-of-truth to move from Markdown files to a live database without rewriting content.
- Demonstrable Competency: The system itself must serve as a proof-of-concept for knowledge graphing, ETL logic and database normalization.