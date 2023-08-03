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

