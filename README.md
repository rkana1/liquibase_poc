# RDS MS SQL Database Deployment Report

## Overview
Successfully deployed Microsoft SQL Server on AWS RDS with automated database migration using Liquibase and GitHub Actions.

## Infrastructure
- **RDS Instance**: SQL Server Express (db.t3.micro)
- **Database**: DB name `poc` with `users` table( Create DB manually with appropriate permissions)
- **Connectivity**: Public access with security group on port 1433
- **Credentials**: Stored securely in GitHub Secrets (`DB_URL`, `DB_USERNAME`, `DB_PASSWORD`)

## Database Schema
Created `changelog.yaml` with Liquibase to manage schema changes:
- **Users Table**: `id` (PK), `first_name`, `last_name`, `email` (unique)
- **Migration**: Automated via GitHub Actions pipeline

## GitHub Actions Pipeline
- **Trigger**: Push to `main` branch (easily configurable for other branches)
- **Steps**: Java setup → Liquibase installation → JDBC driver → Migration execution
- **Status**: Successfully deployed and verified

## Results
->RDS instance operational  
->Database schema deployed  
->Pipeline runs successfully on code push  
