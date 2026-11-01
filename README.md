# Banking Data Analysis

A student project exploring the structure and relationships in a set of banking CSV tables.

## First task

Run notebooks/01_inventory.ipynb to list each CSV, count its rows, inspect its columns and inferred types, and summarize missing values. The notebook reads files from data/raw/ in chunks.

## Data placement

Extract the supplied CSV files into data/raw/ on your own computer. The raw data folder is ignored by Git because the archive includes customer identifiers and financial attributes. Do not commit raw rows or notebook outputs containing personal records.

## Main relationship clues

- accounts.customer_id links accounts to customers.
- transactions.account_id links transactions to accounts.
- cards.customer_id and cards.account_id link cards to customers and accounts.
- card_transactions.card_id links card activity to cards.
- loans.customer_id links loans to customers.
- loan_payments.loan_id links payments to loans.
- support_tickets.customer_id links tickets to customers.
- branch_id links accounts, loans and employees to branches.

These are candidate links based on matching column names. Check key uniqueness and unmatched IDs before relying on them.

## Setup

From the project folder in PowerShell:

    py -3 -m venv .venv
    .\.venv\Scripts\Activate.ps1
    python -m pip install -r requirements.txt

Open the notebook in VS Code or Jupyter and run its cells from top to bottom.
