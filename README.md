# APIMVC8
API for Angular Front End

## Overview
This is a .NET Core 8 Web API designed to serve as a RESTful backend for Angular frontend applications.

## Features
- **ASP.NET Core 8** - Latest .NET framework
- **RESTful API** - Standard HTTP methods for CRUD operations
- **CORS Support** - Configured for Angular development (localhost:4200, 4201)
- **Swagger/OpenAPI** - Interactive API documentation at `/swagger`
- **Sample Endpoints** - WeatherForecast controller demonstrating API usage

## Prerequisites
- .NET 8.0 SDK or later
- Visual Studio 2022, VS Code, or Rider (optional)

## Getting Started

### Build the Project
```bash
cd APIMVC8
dotnet build
```

### Run the API
```bash
cd APIMVC8
dotnet run
```

The API will start on:
- HTTP: `http://localhost:5026`
- HTTPS: `https://localhost:7088`

### Access Swagger UI
Open your browser and navigate to:
```
http://localhost:5026/swagger
```

## API Endpoints

### WeatherForecast
- **GET** `/WeatherForecast` - Returns a list of weather forecasts
  - Response: Array of weather forecast objects with date, temperature (C/F), and summary

## CORS Configuration
The API is configured to accept requests from:
- `http://localhost:4200` (default Angular dev server)
- `http://localhost:4201` (alternative Angular dev port)

Credentials are allowed for authenticated requests.

## Project Structure
```
APIMVC8/
├── Controllers/           # API Controllers
│   └── WeatherForecastController.cs
├── Properties/
│   └── launchSettings.json
├── Program.cs            # Application entry point & configuration
├── WeatherForecast.cs    # Data model
├── appsettings.json      # Application settings
└── APIMVC8.csproj       # Project file
```

## Development

### Add New Controllers
Create new controller classes in the `Controllers` folder:
```csharp
[ApiController]
[Route("[controller]")]
public class MyController : ControllerBase
{
    [HttpGet]
    public IActionResult Get()
    {
        return Ok("Hello from MyController");
    }
}
```

### Configuration
Edit `appsettings.json` to modify logging levels and other settings.

### HTTPS Development Certificate
Trust the development certificate:
```bash
dotnet dev-certs https --trust
```

## License
This project is open source.

