# Person Registry Service

![Java](https://img.shields.io/badge/Java-17-orange)
![Spring Boot](https://img.shields.io/badge/Spring_Boot-3.0-green)
![Docker](https://img.shields.io/badge/Docker-enabled-blue)
![Build Status](https://github.com/northbae/person-registry-service/actions/workflows/ci.yml/badge.svg)

A RESTful API designed to manage person records. This project demonstrates a production-ready development cycle, including containerization, automated testing, and Continuous Deployment to the cloud.

**Live Demo:** [https://person-registry-service.onrender.com/api/swagger-ui/index.html#](https://person-registry-service.onrender.com/api/swagger-ui/index.html#)

## Tech Stack
- **Language:** Java 17
- **Framework:** Spring Boot (Web)
- **Database** PostgreSQL, Liquibase
- **Documentation:** OpenAPI 3.0 (Swagger)
- **Testing:** JUnit 5, Mockito
- **Containerization:** Docker
- **CI/CD:** GitHub Actions
- **Cloud Provider:** Render

## Key Features
- **REST Standards:** Strict adherence to HTTP status codes (201 Created, 404 Not Found, etc.) and headers (Location).
- **Automated Pipeline:** Every push to `main` triggers build, tests, Docker image creation, and deployment.
- **Test Coverage:** Unit tests for service layer using Mockito.
- **API Documentation:** Auto-generated Swagger UI.

## API Endpoints

| Method | Endpoint | Description | Status |
| :--- | :--- | :--- | :--- |
| `GET` | `/api/v1/persons` | Get all persons | 200 OK |
| `GET` | `/api/v1/persons/{id}` | Get person by ID | 200 OK / 404 Not Found |
| `POST` | `/api/v1/persons` | Create a new person | 201 Created (Location Header) |
| `PATCH` | `/api/v1/persons/{id}` | Update person details | 200 OK |
| `DELETE` | `/api/v1/persons/{id}` | Remove a person | 204 No Content |

## CI/CD Workflow
The project uses **GitHub Actions** for the CI/CD pipeline:
1. **Build & Test:** Code compilation and execution of unit tests.
2. **Dockerize:** Building a Docker image.
3. **Deploy:** Automatic deployment to Render platform upon successful build.

## How to Run Locally

1. **Clone the repository**
```bash
git clone https://github.com/your-username/person-registry-service.git
```
2. **Run with Docker**
```Bash
docker build -t person-service .
docker run -p 8080:8080 person-service
```
