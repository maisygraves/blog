---
title: "engineering a career knowledge graph: why I built my portfolio as a database"
category: note
skills: [data-storage, data-retrieval, automation, logical-reasoning]
techstack: [Linux, HTML, CSS, Git, GitHub, Jekyll, Visual-Studio-Code]
---

Most portfolios are "write-only" memory. Projects are summarized, published and then sit in a linear timeline. But as a data scientist, I view my work differently. I don't just see a list of projects; I see an evolving network of skills, tools and competencies that grow over time.

To capture this, I built **b-Log**, a personal knowledge graph and portfolio engine designed to treat my professional development like a data engineering problem.

# The Problem: The "Flat File" Portfolio
Standard blogs use tags which don't enforce types or ensure consistency and they make it difficult to answer complex questions like, "Show my every project where I used Python for data retrieval but didn't use a SQL backend."

I wanted to move beyond "tagging" and toward a **relational understanding** of my work.

## 1. The Data Contract: Schema First
In industry, data quality starts with a contract. Before I wrote a single line of CSS for this site, I defined a strict YAML front matter schema. Every post on this site must adhere to a specific metadata structure:
- category: strictly enforced (project vs note)
- skills: mapped to established frameworks (like Grolemund's)
- tech stack: a defined array of tools (e.g. Python, Postgres, Jekyll)
By treating my Markdown files as structured data inputs, I've ensured that my portfolio is "analytics-ready" from day one.

## 2. From Static Site to Relational Database
Currently, b-Log operates as a static site using Jekyll and Liquid. However, the architecture is designed for a transition to a database-backend ecosystem.

**Current Flow:**
Markdown (front matter) --> Jekyll + Liquid --> GitHub Pages

**The Target State:**
Markdown --> Ingestion Script (Python) --> PostgreSQL --> Data Insights

The goal is to move my "source-of-truth" from a folder of files to a PostgreSQL database. By modeling the backend with amny-to-many relationships (using bridge tables for *post skills* and *post techstack*), I can perform complex queries on my own career. This is a direct practice in database design, normalization and ETL logic.

## 3. Why This Matters for Data Science
Building a portfolio this way isn't just about showing off projects; it's about demonstrating the core competencies required in modern data roles:
- **Knowledge Graphing:** Understanding that data is most valuable when it's connected, not siloed.
- **Scheme Enforcement:** Recognizing that messy data leads to messy insights.
- **Iterative Deployment:** Using modular components and clean documentation to ensure my "knowledge engine" is reproducible.

# The Vision: A Queryable Career
The ultimate goal of b-Log is to create a bi-directional experience. When you click on a skill like *Postgres*, you shouldn't just see a list of posts but also a curated view of every project I've built with that tool, the notes I took while learning it, and the other skills that frequently overlap with it.

It's not just a blog, it's a living map of what I know and how I learned it.

<hr>

### What's Next?
I am currently refining the Python script that will handling the ingestion from my Markdown files into my local Postgres instance. Stay tuned for a technical deep-dive into the SQL schema and the ETL challenges of syncing a static site with a relational database.