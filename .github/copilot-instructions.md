# Copilot Instructions for .NET Backend and React/Vite Frontend

## General Copilot Usage Guidelines

- Follow the existing patterns in the codebase.
- Propose small, incremental suggestions.
- Avoid generating boilerplate unless explicitly requested.
- Respect existing naming conventions and folder structure.
- Add XML or JSdoc comments where appropriate.

---

## .NET Backend Development & Testing

### Project Structure Overview

- **src/backend/[projectname]** – .NET 8 Web API
    |-- Controllers/
    |-- Services/
    |-- Repositories/
    |-- Models/
    |-- Migrations/
    |-- Program.cs
    |-- Startup.cs

### Architecture and Code Practices

- Use **.NET 8** ASP.NET Core Web API with Controller-based routing.
- Use **Dependency Injection** and **SOLID principles**.
- Use **Entity Framework Core** for data access (code-first approach).

### Coding Best Practices

- Use **C#** and **.NET** best practices for backend code.
- Document public APIs with XML comments and **Swagger/OpenAPI**.
- Always return **ActionResult<T>** from controllers.
- Map domain models to DTOs using **AutoMapper**.
- Use **FluentValidation** for request validation.
- Configure error handling using `UseExceptionHandler` middleware.
- Use **IAsyncEnumerable** or `async/await` for all IO-bound operations.

### Backend Testing

- Use **xUnit** for unit and integration tests.
- Mock dependencies using **Moq**.
- Use **TestServer** from `Microsoft.AspNetCore.TestHost` for end-to-end testing.
- Validate all APIs using Swagger and automated integration tests.

---

## React/Vite Frontend Development & Testing

### Project Structure Overview

- **src/frontend/** – React 18 + Vite with TypeScript
    |-- src/
    |-- components/
    |-- pages/
    |-- hooks/
    |-- services/
    |-- types/
    |-- utils/

### Code Style and Patterns

- Use **TypeScript** for all components and logic.
- Use React **functional components** and hooks (e.g., useState, useEffect).
- Use **React Router v6+** for navigation.
- State management via **Zustand** or **React Context** (lightweight), or **TanStack Query** for async data.
- Organize files by feature/module.
- Style latest version of Shadcn and Tailwind CSS.

### Coding Best Practices

- Use `axios` with interceptors for API calls.
- Store environment variables in `.env`.
- Validate forms using **React Hook Form + Zod**.
- Follow accessibility and ARIA standards.
- Write unit and integration tests using Jest and React Testing Library.
- Mock API calls in tests using MSW (Mock Service Worker) or similar tools.
- Use Vite for fast development and optimized builds.
- Follow accessibility (a11y) best practices in UI components.
- Document components and props with JSDoc or TypeScript types.

### Frontend Testing

- Use **Vitest** for unit and integration tests.
- Use **Testing Library** (`@testing-library/react`) for UI tests.
- Use **Mock Service Worker (MSW)** to mock backend APIs.
- Ensure all components and pages have test coverage >80%.

---

## Shared Testing and Validation Best Practices

### Linting & Formatting

- Backend: `dotnet format` and `StyleCop`
- Frontend: ESLint + Prettier

### CI/CD Validations

- All commits should pass:
  - Linting
  - Type checks
  - Unit tests
- Use GitHub Actions for CI:
  - `.NET build & test`
  - `npm test` for frontend
  - Code coverage reports (e.g., Coverlet for backend, Vitest for frontend)

### Tools

| Area           | Tool/Lib               |
|----------------|------------------------|
| Backend Testing| xUnit, Moq, TestServer |
| Frontend Testing| Vitest, Testing Library, MSW |
| Linting        | ESLint, Prettier       |
| Validation     | FluentValidation, Zod  |
| CI/CD          | GitHub Actions         |

---

_These instructions are intended to guide Copilot and contributors in maintaining high standards for backend and frontend development in this repository._
