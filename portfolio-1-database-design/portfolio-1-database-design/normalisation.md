Normalisation: Bank/Fintech Platform
 1. Introduction

Normalisation is the process of organising database tables to reduce unnecessary data duplication and improve data integrity. The Bank/Fintech Platform database is designed using the principles of First Normal Form (1NF), Second Normal Form (2NF), and Third Normal Form (3NF).

2. First Normal Form (1NF)

Each table stores individual values in its columns, and each record can be uniquely identified by a primary key. For example, customer names and contact details are stored as separate attributes rather than combining multiple values in one field.

3. Second Normal Form (2NF)

The tables use primary keys to identify records. The design avoids partial dependencies because the proposed tables use single-column primary keys, meaning non-key attributes depend on the whole primary key.

4. Third Normal Form (3NF)

Non-key attributes are stored in the table where they logically belong. For example, customer contact details are stored in `Customers`, while account details are stored in `Accounts`. This avoids repeating customer information in every account record.

Transaction audit events are stored in `TransactionLogs`, separate from the main transaction records. Transfer-specific details are stored in `Transfers`, rather than adding source and destination account fields to every transaction.

5. Benefits

The proposed normalised design helps reduce duplication, supports consistent updates, and makes it easier to maintain customer, account, transaction, and audit information. It also provides a foundation for reliable financial transaction processing.

 6. Conclusion

The database is designed with 1NF, 2NF, and 3NF principles in mind. During implementation, the schema and its functional dependencies will be reviewed to verify that the design satisfies these normalisation requirements.
