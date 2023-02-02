---
layout: post
title: Data Warehouses
---

* **OLTP Database**  
Online Transactional Processing  
  - usually called a 'database'
  - data is normalized to save storage space & for consistency reasons
  - joins and queries are slow
  - optimized for write operations
  - updated frequently
  - stores data that is currently in active use: older records can be purged & moved to backups
* **OLAP Database**  
Online Analytical Processing   
  - usually called a 'data warehouse'
  - data is de-normalized
  - joins and queries are fast
  - optimized for read operations
  - not updated frequently; instead, data is appended in large batches
  - stores historical records, often from multiple providers
* 
