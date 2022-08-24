# BankApp

The goal of this project is to build a functioning application for fictional Bank. A colleague has already started working on the project and you will be taking over from them.

The project is split into phases:

### Phase 1: Console application
In this phase you will be building a working console app that has most of the core logic. You will fix bugs and implement some missing logic


### Phase 2: Persitent data
In this phase you will create a database, and update your solution so that data is stored in the database enabling the bank to preserve the bank account records after the application is closed


### Phase 3: Webservice
In this phase the users have requested a nicer online user interface. A separate team will be building the online user interface but you task is to build a webservice with the endpoints for the operations they want to perform on the bank app.


## Solution overview:
The solution contains a .NET6 library (Moneybox.App) which is structured into the following 3 folders:

* Domain - this contains the domain models for a user and an account, and a notification service.
* Features - this contains two operations, one which is implemented (transfer money) and another which isn't (withdraw money)
* DataAccess - this contains a repository for retrieving and saving an account (and the nested user it belongs to)



## The task
See User Stories Excel sheet for the details

The task is to create a banking account App with the following features:
- Add an account
- Withdraw money from an account
  - Users are not allowed to withdraw more money than what they have in their account.
- Pay money into an account
  - Usere are not allowed to pay more than a certain amount in a single transaction.
- Transfer money between 2 accounts
- For audit purposes we keep track of the total amount withdrawn and the total amount paid-in. If the total amount paid-in is more than 100,000,000 we suspect fraud an you should prevent and more pay-ins or withdrawals happening on that account 
- Users should get notified if balance falls below a certain amount



Tech features:
- The accounts and balances are stored in a database
- There is a webservice



