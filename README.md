# BestStoreMVC Application

## Overview
BestStoreMVC is an ASP.NET Core MVC web application that demonstrates how to perform CRUD (Create, Read, Update, Delete) operations using Entity Framework Core and SQL Server. The application allows users to manage a list of products, including uploading images for each product.

## Features
- List products
- Create a new product
- Edit an existing product
- Delete a product
- Upload and display product images

## Prerequisites
- .NET 6.0 SDK
- SQL Server
- Visual Studio 2022 (recommended for development)

## Configuration
### appsettings.json
Ensure your `appsettings.json` file contains the correct connection string to your SQL Server instance.

```json
{
  "Logging": {
    "LogLevel": {
      "Default": "Information",
      "Microsoft.AspNetCore": "Warning"
    }
  },
  "AllowedHosts": "*",
  "ConnectionStrings": {
    "DefaultConnection": "Data Source=LAPTOP-EOGAQESG\\SQLEXPRESS;Initial Catalog=BestStoreDb;Integrated Security=True;Trust Server Certificate=True"
  }
}
```
## Database Setup
- Open the Package Manager Console in Visual Studio. Run the following commands to create the database and apply the migrations:

```powershell
Add-Migration InitialCreate
Update-Database
```
This will create the BestStoreDb database with the required tables.

## Running the Application
- Open the solution in Visual Studio.
- Ensure the connection string in appsettings.json is correct.
- Open the Package Manager Console and run the migration commands mentioned above.
- Build and run the application.

## Contributing
Contributions are welcome! Please create an issue or pull request for any features, bug fixes, or improvements.
