# Entities and Attributes

## 1. Customers
Stores the personal and contact information of each customer.

- `customer_id`
- `first_name`
- `last_name`
- `email`
- `phone`
- `created_at`

## 2. Accounts
Stores each customer's financial account information.

- `account_id`
- `customer_id`
- `account_number`
- `account_type`
- `balance`
- `status`
- `created_at`

## 3. Transactions
Records deposits, withdrawals, transfers, and reversals.

- `transaction_id`
- `transaction_type`
- `amount`
- `status`
- `transaction_date`

## 4. TransactionLogs
Stores audit events relating to transactions.

- `log_id`
- `transaction_id`
- `event_type`
- `event_details`
- `created_at`

## 5. Transfers
Stores the source and destination accounts for each transfer.

- `transfer_id`
- `transaction_id`
- `source_account_id`
- `destination_account_id`
