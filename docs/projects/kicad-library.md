---
layout: default
title: Custom KiCad Database
parent: Projects
nav_order: 2
---

# KiCad SQL Database Library
{: .no_toc }

## Overview
I moved my component management from local libraries to a centralized SQLite database.

## Schema Design
The database uses a specific schema to separate **Symbols** (logical) from **Footprints** (physical).
