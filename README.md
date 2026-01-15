# Project:  b-Log 
A personal website to showcase professional skills, projects, notes and resources. 

## Purpose

Portfolio
- showcase personal projects and technical skills
- portfolio for potential opportunities

Technical Practice
- front-end tools: HTML/CSS
- Git workflows and source code management
- file organization and reproducibility
- (planned) database design with PostgreSQL

Collaboration/Contribution
- facilitate collaboration on problems and projects
- share thoughts and approaches that may help others

Non-Goals
- monetization
- notoriety

## Audience
- prospective employers
- peers and collaborators
- personal/professional contacts
- myself (technical skill development)

# Features

## Navigation
- access the home page at any time
- access any page from the home page
- access skills and tools from home page and associated posts
- access external sites from home page
- access GitHub repos from project posts 

## Content Browsing
- projects page for completed studies with links to GitHub repos
- notes page discussing projects
- list of posts by category, labeled with associated skills & tools
- resources page with curated references
- page per skill/tool with list of associated posts

## External Links
- LinkedIn for resume
    - from "resume" in nav bar 
    - from social icons navigation
- GitHub for source code
- Bluesky for interaction and casual sharing

## Learning/Practice
- version control and Git workflow
- source code and file management
- iterative development
- modular deployment, small objects/components and good documentation
- front-end design
- back-end (database) integration

## Collaboration Features
- make work visible and reproducible
- publish technical ideas and approaches for others to view

# Requirements

## Functional
- multi-page: home, projects, notes, resources, skills, tools
- navigation menu
- skills & tools navigation from home-page
- external links: LinkedIn, GitHub, Bluesky
- access skills & tools from post listings
- access GitHub repos from project posts
- simple design - not SWE-focused
- platform for technical practice
- database-driven pre-build (planned)

## Non-Functional 
- clean design, not code-heavy
- designed for easy future data-base driven content pre-build
- enables iterative development

## Future
- data maintenance via PostgreSQL

# System Architecture

## Current State 
browser --> front-end --> GitHub pages

## Future State
database
|>
build script --> YAML/JSON files --> Jekyll + Liquid templates
|>
GitHub Pages --> user browser

# Front End
HTML, CSS
Jekyll + Liquid 

# Back End (planned)
PostgreSQL
- store and retrieve content
- store and retrieve project data
- potential educational use-cases

# Deployment and Maintenance

## Hosting & Development
- hosted on GitHub Pages
- built from Jekyll and Liquid templates
- content pre-build from YAML file 

## Deployment Steps
- run Jekyll to generate static pages
- push pages to GitHub repo
- ensure cohesion across GitHub, LinkedIn and Bluesky

## Maintenance
- iterative additions and edits to content
- Git/GitHub version control system
- content management in YAML
- (planned) data/content management in PostgreSQL
