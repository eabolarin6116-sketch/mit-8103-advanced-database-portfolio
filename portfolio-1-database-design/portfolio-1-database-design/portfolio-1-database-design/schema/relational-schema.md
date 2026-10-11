# Relational Schema: Bank/Fintech Platform

This schema defines the tables required to store customers, accounts, transactions, transfer details, and transaction audit logs.

## 1. Customers

- `customer_id` — INT, Primary Key
- `first_name` — VARCHAR(50), NOT NULL
- `last_name` — VARCHAR(50), NOT NULL
- `email` — VARCHAR(100), UNIQUE, NOT NULL
- `phone` — VARCHAR(20)
- `created_at` — TIMESTAMP, NOT NULL

## 2. Accounts

- `account_id` — INT, Primary Key
- `customer_id` — INT, Foreign Key referencing `Customers(customer_id)`
- `account_number` — VARCHAR(20), UNIQUE, NOT NULL
- `account_type` — VARCHAR(20), NOT NULL
- `balance` — DECIMAL(15,2), NOT NULL
- `status` — VARCHAR(20), NOT NULL
- `created_at` — TIMESTAMP, NOT NULL

## 3. Transactions

- `transaction_id` — INT, Primary Key
- `account_id` — INT, Foreign Key referencing `Accounts(account_id)`, nullable for transfers
- `transaction_type` — VARCHAR(20), NOT NULL
- `amount` — DECIMAL(15,2), NOT NULL
- `status` — VARCHAR(20), NOT NULL
- `transaction_date` — TIMESTAMP, NOT NULL

## 4. TransactionLogs

- `log_id` — INT, Primary Key
- `transaction_id` — INT, Foreign Key referencing `Transactions(transaction_id)`
- `event_type` — VARCHAR(50), NOT NULL
- `event_details` — TEXT
- `created_at` — TIMESTAMP, NOT NULL

## 5. Transfers

- `transfer_id` — INT, Primary Key
- `transaction_id` — INT, Foreign Key referencing `Transactions(transaction_id)`, UNIQUE, NOT NULL
- `source_account_id` — INT, Foreign Key referencing `Accounts(account_id)`
- `destination_account_id` — INT, Foreign Key referencing `Accounts(account_id)
