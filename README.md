# c-workflow
## High-Level Architecture
+-------------------+         +-------------------+
|   Shared Library  |         |   Microservice    |
|-------------------|         |-------------------|
| - Data Models     | <-----> | - Controllers     |
| - DTOs            |         | - Services        |
| - Validation      |         | - Repository      |
| - Mapping         |         | - API Endpoints   |
+-------------------+         +-------------------+
        ^                               |
        |                               v
+-------------------+         +-------------------+
| Other Services    |         | Database / Storage|
| (import library)  |         | (SQL, NoSQL, etc.)|
+-------------------+         +-------------------+

Shared Library: A NuGet package or internal project reference containing your data models, DTOs, and validation logic.

Microservice: A .NET Core Web API project that references the library, adds business logic, and exposes endpoints.

Other Services: Can either consume the library directly (if in .NET) or call the microservice API (if polyglot).

