# Fire SME

### Background

This is an Insurance Prdouct created on top of Insillion SaaS Platform. 
Insillion SaaS platform is owned by GoDB Tech, Chennai.
Insurance Carriers use this to Cloud enable their Sales, Underwriting, Issuance and Administration.
Insurers across LOBs - Personal Lines, Commercial Lines, Life and Health - use this extensively.

The base platform provides multiple portals and interfaces for
* B2E: Sales, Underwriting, Operations, Customer Service, Finance
* B2B: Agency, Brokers, Affinity Partners (Bancassurance, Retailers..)
* B2C: Corporates, Small/Medium Enterprises
* API: Large Broking Houses, Syndicates
* SDK: Embedding in portals/apps of Financial Institutions, ECommerce providers, Wellness providers
---
### About this Product

**Fire SME** is a readymade Software Suite for **Commercial Property (aka Fire)** Insurance used in India, GCC, ASEAN countries.
This software suite provides following capabilities

* Submission Clearance (Online Validation)
* Risk Assessment and Pricing (Forms, Rating)
* Underwriting (Workbench, Rate Mangement, Rules, Clauses)
* Quote generation (PDF, Emails)
* Payment Interfaces
* Issuance of Policies (PDF Schedules)
* Endorsements / Mid-term adjustments
* Renewals (coming soon)
* IT console
---
### Pre-requisites

To use this software product, you would need

* Insillion SaaS platform subscription
* DevOps: Insillion Fire SME product deployed in your instance
* BA: Upload insurer specific rates, masters, clauses
* BA: Configure insurer specific workflows, validations
* Dev: Upload insurer specific PDF templates
---
### Folder structure

This repository contains following folders (target users: DepOps team)
* `docs` : Feature list, Product Spec, Test Scenarios, Manuals
* `ideploy`: Used by deployment script of Insillion for automated deployments (with default config) into environments. Use this only for the first time you deploy into your instance. Feel free to change the configuration and maintain in your respective project Git repos.
* `masters`: Default / Sample master data that get shipped with the software. This can be used to view the functioning of the product. Its advised to clear this and replace with Insurer specific master data.
* `rater`: This would contain the core Rating Excel that contains the rating logic, (wider) rules, (wider) validations etc
---
