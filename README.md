# install-providers-dotnet
install packages for various database providers


# SQL Server
Database First --WINDOWS

* Install-Package Microsoft.EntityFrameworkCore
* Install-Package Microsoft.EntityFrameworkCore.SqlServer
* Install-Package Microsoft.EntityFrameworkCore.Tools

Connection String:
Scaffold-DBContext "Server=<your-server-database>;Database=<your-name-database>;User=<your-user-database>;Pwd=<your-password-database>" Microsoft.EntityFrameworkCore.SqlServer -OutputDir Models -Force -nopluralize

NET 7

Scaffold-DBContext "Server=<your-server-database>;Database=<your-name-database>;User=<your-user-database>;Pwd=<your-password-database>;TrustServerCertificate=True" Microsoft.EntityFrameworkCore.SqlServer -OutputDir Data -Force -nopluralize

In appsettings.json: 

  "ConnectionStrings": {
    "DevConnection": "Server=<your-server-database>;Database=<your-name-database>;User=<your-user-database>;Pwd=<your-password-database>"
  }
------------------------------------------------------------------------------------------------------  
 Database First --MAC
 
* dotnet add package Microsoft.EntityFrameworkCore
* dotnet add package Microsoft.EntityFrameworkCore.Tools
* dotnet add package Microsoft.EntityFrameworkCore.SqlServer
* dotnet add package Microsoft.EntityFrameworkCore.Design

—All commands Entity Framework Core
  
dotnet ef

Connection String:
dotnet ef dbcontext Scaffold "Server=<your-server-database>; Initial Catalog=<your-name-database>;User ID=<your-user-database>;Password=<your-password-database>" Microsoft.EntityFrameworkCore.SqlServer --output-dir Models --no-pluralize

------------------------------------------------------------------------------------------------------
Code First --MAC
* dotnet add package Microsoft.EntityFrameworkCore
* dotnet add package Microsoft.EntityFrameworkCore.Tools
* dotnet add package Microsoft.EntityFrameworkCore.SqlServer
* dotnet add package Microsoft.EntityFrameworkCore.Design

—All commands Entity Framework Core
dotnet ef

—Add migration
  
dotnet ef migrations add ‘aquí detallo un texto para la nueva migración’
  
—Remove migration
  
dotnet ef migrations remove
  
—Update database
  
dotnet ef database update


# MySQL
Database first


Packages by Package Manager Console
* Install-Package Microsoft.EntityFrameworkCore.Design
* Install-Package Microsoft.EntityFrameworkCore.Tools
* Install-Package Pomelo.EntityFrameworkCore.MySql
* Install-Package MySql.Data.EntityFrameworkCore.Design

Connection String:
Scaffold-DbContext "server=<your-server-database>;port=3306;uid=<your-user-database>;pwd=<your-password-database>;database=<your-name-database>" Pomelo.EntityFrameworkCore.MySql -OutputDir Data -nopluralize

In appsettings.json: 

  "ConnectionStrings": {
    "DevConnection": "server=<your-server-database>;port=3306;uid=<your-user-database>;pwd=<your-password-database>;database=<your-name-database>" 
  }
  
  # SONAR in MAC M1
  
  docker run -d -p 8084:9000 mwizner/sonarqube:8.7.1-community


