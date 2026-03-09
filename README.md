# Account Pulse CRM - Palantir Foundry

## Overview
Account Pulse is a CRM application built in **Palantir Foundry** to help users manage company accounts and contacts through interactive dashboards and ontology-driven workflows.

The project uses raw **company** and **people** datasets as source data, cleans and transforms them in **Pipeline Builder**, links contacts to their associated accounts, and presents the results through a **Workshop** application.

## Project Goal
The goal of this project was to create a functional CRM experience in Foundry by translating a business need into an interactive data application.

## Data Sources
This project uses two raw datasets:
- `raw_companies`
- `raw_people`

These datasets serve as the foundation for account and contact records in the CRM.

## Foundry Components Used
- **Pipeline Builder** for data cleaning, transformation, and linking
- **Ontology** for business object modeling
- **Workshop** for building the interactive CRM interface
- **Actions** for enabling user interaction from the dashboard
- **Link Types** for connecting contacts to accounts

## Data Preparation and Transformation

### Company data
The company dataset was cleaned and transformed in Pipeline Builder by:
- trimming whitespace in address fields
- standardizing revenue tier values
- generating a `company_id`
- hashing the generated company identifier

The transformed output was loaded into the **Companies** table.

### People data
The people dataset was cleaned and transformed in Pipeline Builder by:
- cleaning phone numbers using regex replacement
- standardizing phone-related values
- removing duplicate records
- generating a `contact_id`
- hashing the generated contact identifier
- deriving phone status information

The transformed output was loaded into the **People** table.

### Account Linking
The transformed people and companies datasets were joined using **company name** to identify whether a contact could be linked to an existing account.

A follow-up transformation was applied to create an account-linked status for contacts and associate them with the relevant company where a match existed.

## Ontology Design
The application includes:
- **2 Object Types**
  - `Account`
  - `Contact`

- **1 Link Type**
  - links a contact to an account

This ontology structure supports CRM-style navigation and interaction between companies and their associated people.

## Workshop Application
The **Account Pulse CRM** Workshop application provides interactive dashboards for both accounts and contacts.

### Account dashboard
The account dashboard includes:
- KPI tiles such as total accounts, total revenue, and industry count
- charts for revenue tier distribution and industry-level account counts
- filter panel for revenue tier, industry, and revenue range
- company table with account details
- action button to create a new company

### Contact dashboard
The contact dashboard includes:
- KPI tiles such as total contacts, total companies, and linked companies
- charts showing account-linked vs non-linked contacts and company-wise contact counts
- filter panel for name, company, account linked status, and phone validity
- contact table with details such as name, email, phone number, company, and linked account status
- action buttons to add a new contact, delete a contact, and update phone number

## Key Functionality
- Load raw company and people data into Foundry
- Clean and standardize business records
- Deduplicate contacts
- Link contacts to accounts when a matching company exists
- Model CRM objects in Ontology
- Provide interactive dashboards in Workshop
- Trigger actions directly from the application interface

## Project Structure in Foundry
- **Data**: raw source files
- **Transform**: Account Pulse pipeline and transformed outputs
- **Workshop**: CRM dashboards and actions

## Screenshots
This repository includes screenshots of:
- pipeline overview
- company transformations
- people transformations
- accounts dashboard
- contacts dashboard

## Skills Demonstrated
- Palantir Foundry
- Pipeline Builder
- Data Cleaning and Transformation
- Data Linking / Record Association
- Ontology Modeling
- Workshop Dashboard Development
- Action Configuration
- CRM Application Design

## Technical Skills Relevance
This project demonstrates hands-on experience with **Palantir Foundry** for building data pipelines, ontology-backed applications, and interactive business workflows.

## Author
Mithali Manjunath
