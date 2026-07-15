# SimpleShop

A modern e-commerce application built with Java 21, Spring Boot 3, Angular 22, PostgreSQL, and Docker.

## Tech Stack

### Backend
- Java 21 (LTS)
- Spring Boot 3.5.16
- Spring Security *(planned)*
- Spring Data JPA (Hibernate)
- Spring Boot Actuator
- Spring Boot Validation
- PostgreSQL 17
- Lombok
- Maven Wrapper

### Frontend
- Angular 22 *(planned)*
- Standalone Components
- Signals
- Angular Material
- Tailwind CSS

### DevOps
- Docker
- Docker Compose
- GitHub Actions *(planned)*

---

## Features

| Feature | Status |
|---|---|
| Project Setup & Infrastructure | ✅ Done |
| Product Catalog | 🔲 Not started |
| Product Details | 🔲 Not started |
| Search Products | 🔲 Not started |
| Shopping Cart | 🔲 Not started |
| Authentication | 🔲 Not started |
| Orders | 🔲 Not started |
| Admin Dashboard | 🔲 Not started |

---

## Project Status

🚧 **In Development** — Infrastructure & scaffold complete. Feature implementation not yet started.

### What's built
- Spring Boot application entry point
- Package structure: `controller`, `service`, `repository`, `entity`, `dto`, `config`, `exception`
- `GET /api/health` endpoint
- Docker Compose with Postgres 17, pgAdmin 4, backend, and frontend services
- Backend Dockerfile (build & run via `mvnw`)
- Frontend Dockerfile stub (Node 22)

### What's pending
- Angular 22 frontend project initialization
- All domain features (products, cart, orders, auth, admin)
- Spring Security + JWT authentication
- Database migration tooling (Flyway)
- CORS configuration
- Unit & integration tests
- GitHub Actions CI/CD pipeline

---

## Next Steps

1. **Initialize Angular frontend** — scaffold Angular 22 project inside `frontend/` with standalone components and Signals
2. **Add Spring Security** — include `spring-boot-starter-security` in `pom.xml` and configure JWT
3. **Product domain** — create `Product` entity → repository → service → REST controller
4. **Database migrations** — replace `ddl-auto: update` with Flyway for version-controlled schema changes
5. **CORS config** — add `CorsConfigurationSource` bean in `config/` for Angular dev server
6. **Write tests** — integration tests with `@SpringBootTest` and unit tests for the service layer
7. **CI/CD** — set up GitHub Actions workflow for build and test on push

---

## Run with Docker

From the project root:

```bash
docker compose up --build
```

Backend:

- http://localhost:8080

---

### Run Locally

Start the PostgreSQL database first:

```bash
docker compose up -d postgres
```

Navigate to the backend project:

```bash
cd backend
```

Run the application:

**Windows**

```bash
mvnw.cmd spring-boot:run
```

**Linux/macOS**

```bash
./mvnw spring-boot:run
```

---

### Build

**Windows**

```bash
mvnw.cmd clean package -DskipTests
```

**Linux/macOS**

```bash
./mvnw clean package -DskipTests
```

---

### Health Endpoints

Application Health

- http://localhost:8080/api/health

Spring Boot Actuator

- http://localhost:8080/actuator
- http://localhost:8080/actuator/health

Expected response:

```text
SimpleShop Backend is Running!
```

---

### Services

| Service | URL | Description |
|---|---|---|
| Backend API | http://localhost:8080 | Spring Boot REST API |
| Health Check | http://localhost:8080/api/health | Backend status |
| pgAdmin | http://localhost:5050 | Database management UI |

### pgAdmin Connection

| Field | Value |
|---|---|
| Host | `postgres` |
| Port | `5432` |
| Database | `simpleshop` |
| User | `postgres` |
| Password | `postgres` |

---

## License

[MIT](LICENSE)
