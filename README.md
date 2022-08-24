# Moneybox Money Withdrawal

The solution contains a .NET core library (Moneybox.App) which is structured into the following 3 folders:

* Domain - this contains the domain models for a user and an account, and a notification service.
* Features - this contains two operations, one which is implemented (transfer money) and another which isn't (withdraw money)
* DataAccess - this contains a repository for retrieving and saving an account (and the nested user it belongs to)

## The task

The task is to create a banking account App with the following features:
- Add/open an account
- Update an account details
- Withdraw money from an account
- Pay into an account
- Transfer money between 2 accounts

- Users should get notified if balance below a certain amount or pay-in limit reached

Tech features:
- The accounts and balances are stored in a database
- There is a webservice


## Database
### Structure
![image](https://user-images.githubusercontent.com/63453969/182586055-7d61554f-6bb3-4fdf-ae48-f27c8ac5cd53.png)

### Sql setup
1. Download Sql server mgt. studio: https://docs.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver15
2. Download sql server express localdb: https://docs.microsoft.com/en-us/sql/database-engine/configure-windows/sql-server-express-localdb?view=sql-server-ver15
3. Create a new db and Run db setup script

### Alternative setup
*Install SQL Server Studio*: [Download](https://docs.microsoft.com/en-us/sql/ssms/download-sql-server-management-studio-ssms?view=sql-server-ver15)

*Setup LocalDB* : [Download and install](https://www.sqlshack.com/install-microsoft-sql-server-express-localdb/) or [direct download](http://download.microsoft.com/download/8/D/D/8DD7BDBA-CEF7-4D8E-8C16-D9F69527F909/ENU/x64/SqlLocalDB.MSI)

*Set up a local db instance using this guide*: [Setup your LocalDB.](https://www.sqlshack.com/how-to-connect-and-use-microsoft-sql-server-express-localdb/)

### Alternative setup 2
[Microsoft guide](https://docs.microsoft.com/en-us/sql/database-engine/configure-windows/sql-server-express-localdb?view=sql-server-ver15)
1. Install using link above or through the Visual Studio Installer, as part of the ASP.NET and web development workload, or as an individual component.
2. It should automatically be running. If it isn't you can start it by running in command prompt
```
SqlLocalDB start MSSQLLocalDB
```
3. Connect to it via SQL Server.    
Server name: (localdb)\MSSQLLocalDB  
Authentication: Windows Authentication
4. Create a new database in SQL Server
5. Run database setup script (to be provided by a colleague)

## Project setup
Create a db project with these libraries:
![image](https://user-images.githubusercontent.com/63453969/182610077-fae29d0d-08ad-4a4e-9277-f912de292d58.png)

### Scaffolding DB:
You can automatically generate the c# code for a db table using scaffolding

https://docs.microsoft.com/en-us/ef/core/managing-schemas/scaffolding?tabs=dotnet-core-cli

1. Set db project SwiftProposal.Data as startup project
2. Open up Package Manager Console
3. Set default project in the package manager window to SwiftProposal.Data 
4. Run below
```
Scaffold-DbContext "data source=[Your db ConnectionString]" Microsoft.EntityFrameworkCore.SqlServer -OutputDir Scaffolded
```

Replace with your db connection string. E.g.
```
Scaffold-DbContext "data source=(LocalDB)\MSSQLLocalDB;initial catalog=Bank;MultipleActiveResultSets=True;App=EntityFramework" Microsoft.EntityFrameworkCore.SqlServer -OutputDir Scaffolded
```

5. I normally copy relevant bits from the Scaffolded folder
6. You can specify specific tables using the -table parameter
