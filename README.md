# Following this tutorial: ASP.NET Core Crash Course - C# App in One Hour
https://www.youtube.com/watch?v=BfEjDD8mWYg

# Problems faced during setup for mac: 
1. Unable to enable migrations for mac due to lack of Package Manager Console in Mac's Visual studio
    - Follow this tutorial to install dotnet ef : https://stackoverflow.com/questions/45382536/how-to-enable-migrations-in-visual-studio-for-mac
    - I had these errors when i ran this command: 
            ```dotnet ef migrations add nameOfMigration ```
            The error that I got was this" 
            ```No project was found. Change the current working directory or use the --project option.```
            Then add at the end the solution of the project that I had in the root
            ```dotnet ef migrations add nameOfMigration --project project.sln```
            But it gave me another error
            ```error MSB4057: The target "GetEFProjectMetadata" does not exist in the project.```
            I realized that it had to be inside the project folder and the csproj file
            ```dotnet ef migrations add nameOfMigration --project Project/Project.csproj```
            And for me this was my solution
2. Need to update database but no package manager console
    - use this command ```dotnet ef database update --project WebDatabaseApp/WebDatabaseApp.csproj```
    - Encounters : ```System.TypeInitializationException: The type initializer for 'Microsoft.Data.Sqlite.SqliteConnection' threw an exception.```
    - Encounters update ```Unrecognized command or argument 'update' ```
    - not fixed yet
2. sql object explorer is not on vs2022 mac
    - Thank you for the suggestion! At this time we don’t have plans to add support for SQL Server Data Tools in Visual Studio for Mac, and we recommend using Azure Data Studio (https://docs.microsoft.com/en-us/sql/azure-data-studio/what-is). There are a lot of features in SSDT when using VS on Windows, and I’d love to know more about specific features you use on a regular basis. If these tools aren’t available in Azure Data Studio, could you please file separate suggestions here to make it easier to vote?
    - Download azure data studio at this link: https://learn.microsoft.com/en-us/sql/azure-data-studio/download-azure-data-studio?view=sql-server-ver16&tabs=redhat-install%2Credhat-uninstall#download-azure-data-studio 
    - Download docker for mac
    - create a docker id: docker.com and click on sign in
    - run the command, rmb to change password ```docker run -e "ACCEPT_EULA=1" -e "MSSQL_SA_PASSWORD=auN6cTFQ288U" -e "MSSQL_PID=Developer" -e "MSSQL_USER=SA" -p 1433:1433 -d --name=sql mcr.microsoft.com/azure-sql-edge```
    - user: SA, pw: auN6cTFQ288U , authentication type: sql login, server: localhost, connection type: microsoft sql server
    - Additional troubleshooting for mac (unlikely to need it): install rosetta- Apple's x86 emulator for ARM and try process again 

