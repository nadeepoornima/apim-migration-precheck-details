# WSO2 APIM Migration DB Pre-Check Scripts
## Overview
This repository contains database pre-check scripts that help capture important information before initiating a **WSO2 API Manager version migration**. These scripts assist in validating the current deployment state and identifying potential risks or special considerations prior to migration.

The scripts are designed to be compatible with multiple database types and have been tested with:

- MySQL
- Microsoft SQL Server
- PostgreSQL

## Pre-Check-AM.sql
This script captures APIM database information and usage statistics.

### Data Captured
- Total API count
- Total application count
- Active access token count
- Service provider count
- Availability of multiple Key Managers (e.g., Default, IS, or custom Key Managers)
- Token type usage (e.g., JWT or Opaque tokens)
- Grant type usage (e.g., Password, Client Credentials, etc.)
- Authorization code usage
- Availability of never-expiring tokens

## Pre-Check-User.sql
This script captures User(shared) database information and usage statistics.

### Data Captured
-Total user count in the primary user store
- Availability of multiple tenants
- Availability of custom roles
- Custom role availability & Secondary user store usage

## How to Use
- Execute the `Pre-Check-AM.sql` script on the APIM database of your source environment.
- Execute the `Pre-Check-User.sql` script on the Shared database or User Store database (if a separate user store is configured) of your source environment.

## Advantages
- Provides prior understanding of the data size of the current deployment.
- Helps estimate how the data size may affect migration duration.  
- Helps identify customer usage of APIM default features and how they may impact the migration and post-migration validation process
