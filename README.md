# install-providers-dotnet
install packages for various database providers


# Comandos básicos .NET CLI (Windows / Mac / Linux, NET 10)

—Crear un proyecto

dotnet new webapi -n NombreProyecto
dotnet new mvc -n NombreProyecto
dotnet new console -n NombreProyecto
dotnet new classlib -n NombreProyecto

—Crear una solución y agregar proyectos

dotnet new sln -n NombreSolucion
dotnet sln add ./NombreProyecto/NombreProyecto.csproj

—Restaurar paquetes

dotnet restore

—Compilar (build)

dotnet build

—Ejecutar el proyecto

dotnet run

dotnet run --project ./NombreProyecto

—Ejecutar con recarga automática (hot reload)

dotnet watch run

—Publicar (build de producción)

dotnet publish -c Release -o ./publish

—Ejecutar pruebas

dotnet test

—Limpiar los artefactos de compilación

dotnet clean

—Ver la versión de .NET instalada / SDKs disponibles

dotnet --version
dotnet --list-sdks

------------------------------------------------------------------------------------------------------

# SQL Server
Database First --VISUAL STUDIO (WINDOWS)

* Install-Package Microsoft.EntityFrameworkCore (10.0.0)
* Install-Package Microsoft.EntityFrameworkCore.SqlServer (10.0.0)
* Install-Package Microsoft.EntityFrameworkCore.Tools (10.0.0)
* Install-Package Microsoft.EntityFrameworkCore.Design (10.0.0)

Connection String:
Scaffold-DBContext "Server=<your-server-database>;Database=<your-name-database>;User=<your-user-database>;Pwd=<your-password-database>;TrustServerCertificate=True" Microsoft.EntityFrameworkCore.SqlServer -OutputDir Models -Force -nopluralize

NET 10

Scaffold-DBContext "Server=<your-server-database>;Database=<your-name-database>;User=<your-user-database>;Pwd=<your-password-database>;TrustServerCertificate=True" Microsoft.EntityFrameworkCore.SqlServer -OutputDir Data -Force -nopluralize

In appsettings.json: 

  "ConnectionStrings": {
    "DevConnection": "Server=<your-server-database>;Database=<your-name-database>;User=<your-user-database>;Pwd=<your-password-database>;TrustServerCertificate=True"
  }
------------------------------------------------------------------------------------------------------  
 Database First --VSCODE (Windows / Mac / Linux, NET 10)
 
* dotnet add package Microsoft.EntityFrameworkCore --version 10.0.0
* dotnet add package Microsoft.EntityFrameworkCore.Tools --version 10.0.0
* dotnet add package Microsoft.EntityFrameworkCore.SqlServer --version 10.0.0
* dotnet add package Microsoft.EntityFrameworkCore.Design --version 10.0.0

—All commands Entity Framework Core
  
dotnet ef

Connection String:
dotnet ef dbcontext Scaffold "Server=<your-server-database>; Initial Catalog=<your-name-database>;User ID=<your-user-database>;Password=<your-password-database>;TrustServerCertificate=True" Microsoft.EntityFrameworkCore.SqlServer --output-dir Models --no-pluralize

------------------------------------------------------------------------------------------------------
Code First --VSCODE (Windows / Mac / Linux, NET 10)
* dotnet add package Microsoft.EntityFrameworkCore --version 10.0.0
* dotnet add package Microsoft.EntityFrameworkCore.Tools --version 10.0.0
* dotnet add package Microsoft.EntityFrameworkCore.SqlServer --version 10.0.0
* dotnet add package Microsoft.EntityFrameworkCore.Design --version 10.0.0

—All commands Entity Framework Core
dotnet ef

—Add migration
  
dotnet ef migrations add 'aquí detallo un texto para la nueva migración'
  
—Remove migration
  
dotnet ef migrations remove
  
—Update database
  
dotnet ef database update


# MySQL
Database first --VISUAL STUDIO (WINDOWS)

Packages by Package Manager Console
* Install-Package Microsoft.EntityFrameworkCore.Design (10.0.0)
* Install-Package Microsoft.EntityFrameworkCore.Tools (10.0.0)
* Install-Package Pomelo.EntityFrameworkCore.MySql (9.0.0) — latest available; targets EF Core 9 but is compatible with .NET 10
* Install-Package MySql.Data (26.7.0)

Connection String:
Scaffold-DbContext "server=<your-server-database>;port=3306;uid=<your-user-database>;pwd=<your-password-database>;database=<your-name-database>" Pomelo.EntityFrameworkCore.MySql -OutputDir Data -nopluralize

In appsettings.json: 

  "ConnectionStrings": {
    "DevConnection": "server=<your-server-database>;port=3306;uid=<your-user-database>;pwd=<your-password-database>;database=<your-name-database>" 
  }

------------------------------------------------------------------------------------------------------
Database first --VSCODE (Windows / Mac / Linux, NET 10)

* dotnet add package Microsoft.EntityFrameworkCore.Design --version 10.0.0
* dotnet add package Microsoft.EntityFrameworkCore.Tools --version 10.0.0
* dotnet add package Pomelo.EntityFrameworkCore.MySql --version 9.0.0
* dotnet add package MySql.Data --version 26.7.0

—All commands Entity Framework Core

dotnet ef

Connection String:
dotnet ef dbcontext scaffold "server=<your-server-database>;port=3306;uid=<your-user-database>;pwd=<your-password-database>;database=<your-name-database>" Pomelo.EntityFrameworkCore.MySql --output-dir Data --no-pluralize

In appsettings.json: 

  "ConnectionStrings": {
    "DevConnection": "server=<your-server-database>;port=3306;uid=<your-user-database>;pwd=<your-password-database>;database=<your-name-database>" 
  }

—Add migration

dotnet ef migrations add 'aquí detallo un texto para la nueva migración'

—Remove migration

dotnet ef migrations remove

—Update database

dotnet ef database update


