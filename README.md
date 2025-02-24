# Ecommerce Backend - Clean Architecture (ASP.NET Core Web API)

🚀 **Ecommerce-Backend** is a scalable and maintainable **Web API** built using **Clean Architecture** with ASP.NET Core. It follows best practices such as **CQRS, Dependency Injection, Repository Pattern, and JWT Authentication** to ensure high performance and security.

---

## 📌 Features
- ✅ **Clean Architecture** - Modular & scalable structure  
- ✅ **ASP.NET Core 8** - Latest framework for backend development  
- ✅ **Entity Framework Core & Dapper** - Database access  
- ✅ **JWT Authentication & Authorization** - Secure API endpoints  
- ✅ **CQRS Pattern** - Improves performance & maintainability  
- ✅ **Unit of Work & Repository Pattern** - Decouples database operations  
- ✅ **Swagger (OpenAPI)** - API documentation & testing  
- ✅ **Dependency Injection (DI)** - Loose coupling & testability  

---

## 📂 Project Structure
The solution follows **Clean Architecture** with different layers:

EcommerceBackend/ │-- 📂 WebAPI/ → Presentation Layer (API Controllers) │-- 📂 Application/ → Business Logic Layer (CQRS, Services, DTOs) │-- 📂 Domain/ → Core Entities & Interfaces │-- 📂 Infrastructure/ → Data Layer (EF Core, Dapper, Repository) │-- 📂 Shared/ → Common Utilities (Helpers, Middleware) │-- 📂 Tests/ → Unit & Integration Tests │-- 📄 appsettings.json → Configuration (DB, JWT, etc.) │-- 📄 Program.cs → Entry Point of API │-- 📄 README.md → Project Documentation

markdown
Copy
Edit

---

## 🛠️ Technologies Used
- **ASP.NET Core 8** - Web API Framework  
- **Entity Framework Core & Dapper** - Database access  
- **MS SQL Server** - Database  
- **JWT Authentication** - Secure login system  
- **MediatR** - Implements CQRS pattern  
- **FluentValidation** - Input validation  
- **AutoMapper** - DTO mapping  
- **Swagger (Swashbuckle)** - API documentation  
- **Unit Tests (xUnit, Moq)** - Test cases  

---

## ⚙️ Prerequisites
- Install [.NET 8 SDK](https://dotnet.microsoft.com/download/dotnet/8.0)  
- Install [SQL Server](https://www.microsoft.com/en-us/sql-server/sql-server-downloads)  
- Install [Postman](https://www.postman.com/) (Optional for API testing)  

---
cd Ecommerce-Backend
2️⃣ Configure Database
Open appsettings.json and update the connection string:
json
Copy
Edit
"ConnectionStrings": {
  "DefaultConnection": "Server=YOUR_SERVER;Database=Ecommerce;Trusted_Connection=True;"
}
3️⃣ Apply Migrations
Run the following commands to create the database:

sh
Copy
Edit
dotnet ef migrations add InitialCreate -p Infrastructure -s WebAPI
dotnet ef database update -p Infrastructure -s WebAPI
4️⃣ Run the Application
sh
Copy
Edit
dotnet run --project WebAPI
The API will be available at: http://localhost:5000 (or Swagger UI at http://localhost:5000/swagger)

🔑 Authentication (JWT)
To get a token, use the /api/auth/login endpoint:
json

{
  "email": "admin@example.com",
  "password": "Admin@123"
}
Use the JWT token in headers for accessing secure endpoints:

Authorization: Bearer YOUR_ACCESS_TOKEN
📮 API Endpoints
Method	Endpoint	Description
POST	/api/auth/register	Register a new user
POST	/api/auth/login	Authenticate & get JWT token
GET	/api/products	Get all products
POST	/api/products	Create a product (Admin only)
GET	/api/orders	Get user orders
POST	/api/orders	Place an order
GET	/api/users/profile	Get user profile (JWT required)
🛠️ Configuration
🔧 Environment Variables
Alternatively, configure environment variables instead of appsettings.json:

sh
Copy
Edit
export ConnectionStrings__DefaultConnection="Server=YOUR_SERVER;Database=Ecommerce;Trusted_Connection=True;"
export Jwt__Key="YourSuperSecureSecretKeyWithAtLeast32Chars!"
🤝 Contribution
🙌 Contributions are welcome!

Fork the repo
Create a branch (feature/new-feature)
Commit changes (git commit -m 'Add new feature')
Push to branch (git push origin feature/new-feature)
Open a Pull Request
📜 License
This project is licensed under the MIT License.

🚀 Happy Coding! 🎯





