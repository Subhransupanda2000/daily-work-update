
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

