.NET Core Web API with EF Core Code-First approach tutorial - https://code-maze.com/net-core-web-api-ef-core-code-first

This is a very neat tutorial on the above subject.  It touches on the following areas

Setting Up the ASP.NET Core Web API Project
Configuring EF Core
Defining the Model
Creating a Context File
Generating the Database from Code Using Migrations
Seeding Data, Reverting Migrations and Creating DB Scripts
Creating the Repository
Creating the API Controller
Testing the API

To see the API in action, first change the connection string if necessary in appsettings.json.  The database itself will be created later but you may need to change the name of the server.  (I opened SQL Server Object Explorer from the View menu, right-clicked the SQL Server instance called (localdb)\ProjectsV13 and choose Properties.)
Then build the project, open Package Manager Console and type update-database to create the database and then press CTRL+F to Start without debugging
Now open Postman, and enter the following

Choose Get from the Drop Down
http://localhost:5000/api/employee     - this gets all employee
http://localhost:5000/api/employee/1   - this gets employee with ID=1

Choose Post and change the URL to http://localhost:5000/api/employee  In the Body option choose raw then JSON and enter the following   - this will add this record into the database
{
    "firstName": "Jim",
    "lastName": "Smith"
}

Choose Put and change the URL to http://localhost:5000/api/employee/1  (or change the 1 to the ID of an employee you know exists)  In the Body option choose raw then JSON and enter the following   - this will update that record.  You can verify this afterwards by doing a Get to the same URL
{
    "firstName": "Jimmy",
    "lastName": "Smith"
}
