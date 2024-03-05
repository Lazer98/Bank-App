This is my bank demo app written in React and Typescript for the frontend and Java with Spring Boot for the Backend.
For the Database I was using MySql origionally but changed it to H2 DB in order to make usage on several places possible.

The user is able to register to the web page and after registering/logging in he can see his Profile ,where he will see all Transactions connected to his bank account.

It is possible to see only the payouts or only the deposits and filter by authenticated, not authenticated , sort by sum, date ascending or date descending or simply search for a specific transfer according to an input field.

To become an admin the programmer has to manually change his user role to "admin" inside the database. In the admin profile he will see all users and all transfers. 
The admin can change the authentication status of a transfer to true by clicking on the red X and confirming the pop-up.

The process of making a new transfer looks as follows: Enter the IBAN or the BankId + BankAccount number in order to find the right bank account. When the back returns a correct bank account the next step will be entering the sum,
the reason of the transfer and the phone number for verification. Then the user gets a sms with a 4 digit code which he has to enter in the form. If it's correct he can proceed to send the money.

The layer of entities communicating with the user is the dto layer which exists for every entity.

A bit about the DB: I have a User1 table which has the join connection to the adress table (OneToOne) and a connection to the bank_account table (OneToOne).The transfer table has two (ManyToMany) join connections with the bank_account table. 

One missing point in the backend is: Token and JWT Authentication:  I had some troubles with the new version of spring boot security (3.2.2), so I didn't implement any jwt and token logic.

