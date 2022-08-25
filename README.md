# install-providers-dotnet
install packages for various database providers


# SQL Server


Install-Package Microsoft.EntityFrameworkCore
Install-Package Microsoft.EntityFrameworkCore.SqlServer
Install-Package Microsoft.EntityFrameworkCore.Tools

Connection String:
Scaffold-DBContext "Server=<your-server-database>;Database=Sales;User=<your-user-database>;Pwd=<your-password-database>" Microsoft.EntityFrameworkCore.SqlServer -OutputDir Models -Force -nopluralize

In appsettings.json: 

  "ConnectionStrings": {
    "DevConnection": "Server=<your-server-database>;Database=Sales;User=<your-user-database>;Pwd=<your-password-database>"
  }


# MySQL
Database first


Packages by Package Manager Console
Install-Package Microsoft.EntityFrameworkCore.Design
Install-Package Microsoft.EntityFrameworkCore.Tools
Install-Package Pomelo.EntityFrameworkCore.MySql
Install-Package MySql.Data.EntityFrameworkCore.Design

Connection String:
Scaffold-DbContext "server=<your-server-database>;port=3306;uid=<your-user-database>;pwd=<your-password-database>;database=<your-name-database>" Pomelo.EntityFrameworkCore.MySql -OutputDir Data -nopluralize

In appsettings.json: 

  "ConnectionStrings": {
    "DevConnection": "server=<your-server-database>;port=3306;uid=<your-user-database>;pwd=<your-password-database>;database=<your-name-database>" 
  }
