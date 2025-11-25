# StockTraders API
### A full-featured stock portfolio & community backend built with ASP.NET Core 8

![.NET 8](https://img.shields.io/badge/.NET-8.0-5C2D91?logo=.net&logoColor=white)
![C#](https://img.shields.io/badge/Language-C%23-blue)
![JWT Auth](https://img.shields.io/badge/Auth-JWT-000000?logo=json-web-tokens)
![Entity Framework Core](https://img.shields.io/badge/ORM-EF%20Core%208-512BD4)
![SQL Server](https://img.shields.io/badge/Database-SQL%20Server-CC2927?logo=microsoft-sql-server)
![Swagger](https://img.shields.io/badge/Docs-Swagger-brightgreen)
![License](https://img.shields.io/badge/License-MIT-yellow)

A clean, production-ready REST API that lets users:
- Register & login (JWT)
- Browse real stocks (via Financial Modeling Prep)
- Build personal portfolios
- Comment on stocks

A fully-featured stock trading backend that allows users to register, log in, browse stocks, manage personal portfolios,
and comment on stocks – perfect for learning clean architecture, JWT authentication, repository pattern, and external API integration.

## Features
- User registration & login with JWT Bearer authentication
- Full CRUD for Stocks, Comments, and user Portfolios
- Many-to-many relationship between Users ↔ Stocks (Portfolio)
- Integration with Financial Modeling Prep (FMP) API for live stock data
- Filtering, searching & pagination
- AutoMapper + strongly-typed DTOs
- Repository & Service pattern with dependency injection
- Swagger / OpenAPI documentation
- Entity Framework Core Code-First migrations

## Project Structure
StockTradersApi/
├── Controllers/        # All API endpoints
├── Data/               # ApplicationDBContext
├── Dtos/               # Request & response DTOs
├── Helpers/            # Query objects (filtering/pagination)
├── Interfaces/         # Repository interfaces
├── Mappers/            # AutoMapper profiles
├── Migrations/         # EF Core migrations
├── Models/             # Entity classes (AppUser, Stock, Comment, Portfolio)
├── Repository/         # Concrete repository implementations
├── Service/            # TokenService + FMPService
├── Extensions/         # ClaimsPrincipal extensions
├── Properties/         # launchSettings.json
├── appsettings.json
├── Program.cs
└── api.csproj

## API Endpoints (Swagger UI → `/swagger`)

| Method | Endpoint                              | Description                        | Auth   |
|--------|---------------------------------------|------------------------------------|--------|
| POST   | `/api/account/register`               | Register new user                  | –      |
| POST   | `/api/account/login`                  | Login → returns JWT token          | –      |
| GET    | `/api/stock`                          | Get all stocks (+ filtering)       | –      |
| GET    | `/api/stock/{id}`                     | Get single stock                   | –      |
| POST   | `/api/stock`                          | Create stock (Admin)               | Admin  |
| PUT    | `/api/stock/{id}`                     | Update stock (Admin)               | Admin  |
| DELETE | `/api/stock/{id}`                     | Delete stock (Admin)               | Admin  |
| GET    | `/api/portfolio`                      | Get logged-in user's portfolio     | Yes    |
| POST   | `/api/portfolio`                      | Add stock to portfolio             | Yes    |
| DELETE | `/api/portfolio?symbol=XXX`           | Remove stock from portfolio        | Yes    |
| GET    | `/api/comment`                        | Get comments (filterable)          | –      |
| POST   | `/api/comment`                        | Create comment on a stock          | Yes    |
| PUT    | `/api/comment/{id}`                   | Update own comment                 | Yes    |
| DELETE | `/api/comment/{id}`                   | Delete own comment                 | Yes    |


## Tech Stack
- ASP.NET Core 8 Web API
- Entity Framework Core 8 (Code First)
- SQL Server / SQLite (easy to switch)
- JWT Authentication
- AutoMapper
- Swashbuckle (Swagger)
- Financial Modeling Prep API

## Credit

This project was originally built by following Teddy Smith’s excellent .NET 8 Web API tutorial series on YouTube.  

## License
MIT © [Shahin Izadi] – happy to connect on LinkedIn – feel free to star if you like it!