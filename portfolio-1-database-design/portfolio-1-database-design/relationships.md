Entity Relationships

1. Customer and Accounts

A customer can own multiple accounts, while each account belongs to one customer. This is a one-to-many relationship.

2. Accounts and Transactions

An account can be involved in multiple financial transactions. Each transaction must be associated with the relevant account or accounts according to its transaction type.

3. Transactions and TransactionLogs

A transaction can generate multiple audit log entries. Each log entry relates to one transaction. This is a one-to-many relationship.

4. Transactions and Transfers

A transaction may have one transfer record when the transaction type is a transfer. Deposits and withdrawals do not require transfer records.

5. Accounts and Transfers

Each transfer has one source account and one destination account. An account can act as the source of many transfers and can also receive many transfers.

6. Business Rules

Every account must belong to a valid customer.

Every transaction must reference the account or accounts involved in the financial operation.

Every transfer must reference a valid source account and destination account.

A transfer must not send money from an account to itself.

Audit logs must retain a record of relevant transaction events for traceability.
