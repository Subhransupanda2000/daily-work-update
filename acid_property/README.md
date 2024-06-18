
# ACID PROPERTY:
* ACID refers to a set of properties that ensure reliable processing of database transactions. ACID is an acronym for Atomicity, Consistency, Isolation, and Durability. These properties are crucial for maintaining 
  data integrity, especially in systems where transactions are executed concurrently.
![Screenshot (900)](https://github.com/Subhransupanda2000/daily-work-update/assets/123824203/d90df188-e416-4e14-89b3-82ba2de5420e)
# ATOMICITY
* The term atomicity defines that the data remains atomic. It means if any operation is performed on the data, either it should be performed or executed completely or should not be executed at all. It further means that the operation should not break in between or execute partially. In the case of executing operations on the transaction, the operation should be completely executed and not partially.

* Example: If Remo has account A having $30 in his account from which he wishes to send $10 to Sheero's account, which is B. In account B, a sum of $ 100 is already present. When $10 will be transferred to account B, the sum will become $110. Now, there will be two operations that will take place. One is the amount of $10 that Remo wants to transfer will be debited from his account A, and the same amount will get credited to account B, i.e., into Sheero's account. Now, what happens - the first operation of debit executes successfully, but the credit operation, however, fails. Thus, in Remo's account A, the value becomes $20, and to that of Sheero's account, it remains $100 as it was previously present.
  
![Screenshot (901)](https://github.com/Subhransupanda2000/daily-work-update/assets/123824203/e8e298c5-d89c-4f16-b8a5-d48536a71a40)

# CONSISTENCY
The word consistency means that the value should remain preserved always. In DBMS, the integrity of the data should be maintained, which means if a change in the database is made, it should remain preserved always. In the case of transactions, the integrity of the data is very essential so that the database remains consistent before and after the transaction. The data should always be correct.

![Screenshot (902)](https://github.com/Subhransupanda2000/daily-work-update/assets/123824203/65b5cd7f-1425-45e2-92a2-551811daf75b)

# ISOLATION:
* The term 'isolation' means separation. In DBMS, Isolation is the property of a database where no data should affect the other one and may occur concurrently. In short, the operation on one database should begin when the operation on the first database gets complete. It means if two operations are being performed on two different databases, they may not affect the value of one another. In the case of transactions, when two or more transactions occur simultaneously, the consistency should remain maintained. Any changes that occur in any particular transaction will not be seen by other transactions until the change is not committed in the memory.

  ![Screenshot (904)](https://github.com/Subhransupanda2000/daily-work-update/assets/123824203/0506e588-89ba-4dc6-a497-b465553965b6)

# Durability
* Durability ensures the permanency of something. In DBMS, the term durability ensures that the data after the successful execution of the operation becomes permanent in the database. The durability of the data should be so perfect that even if the system fails or leads to a crash, the database still survives. However, if gets lost, it becomes the responsibility of the recovery manager for ensuring the durability of the database. For committing the values, the COMMIT command must be used every time we make changes.

Therefore, the ACID property of DBMS plays a vital role in maintaining the consistency and availability of data in the database.
# Transaction management (BEGIN, COMMIT, ROLLBACK, SAVEPOINT)
# 1. BEGIN
* The BEGIN statement (or START TRANSACTION in some systems) is used to start a new transaction. Once a transaction has started, the subsequent SQL statements are executed as part of that transaction.
* START TRANSACTION;
# 2. COMMIT
* The COMMIT statement is used to end the current transaction and make all changes made during the transaction permanent. Once a transaction is committed, the changes are visible to other transactions.
* COMMIT;
# 3. ROLLBACK
* The ROLLBACK statement is used to undo all changes made during the current transaction. This reverts the database to the state it was in before the transaction began.
* ROLLBACK;
# 4. SAVEPOINT
* The SAVEPOINT statement is used to set a point within a transaction to which you can later roll back. This allows for partial rollbacks within a transaction.
* SAVEPOINT savepoint_name;
# ISOLATION LVELS:
* Transaction isolation levels define the degree to which the operations in one transaction are isolated from those in other concurrent transactions. The isolation level affects how and when the changes made by 
* one operation become visible to other concurrent operations. Different isolation levels balance between performance and the strictness of data consistency guarantees.

* The SQL standard defines four isolation levels, each providing a different level of protection against the phenomena of dirty reads, non-repeatable reads, and phantom reads:

* Read Uncommitted,
Read Committed,
Repeatable Read,
Serializable.
