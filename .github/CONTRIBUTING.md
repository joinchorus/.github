# Contributing to Chorus

Thank you for your interest in contributing to **Chorus**! We welcome contributions from developers of all skill levels.

Chorus is an open-source anonymous discussion platform with native Git-backed append-only persistence. Full technical documentation and developer guides are available at [docs.joinchorus.app](https://docs.joinchorus.app).

---

## Getting Started

### Prerequisites
- **Go**: 1.22 or higher
- **Node.js**: 22 or higher
- **Git**: 2.30 or higher

### Local Development Setup

1. **Fork and clone the repository**:
   ```bash
   git clone https://github.com/YOUR_USERNAME/chorus.git
   cd chorus
   ```

2. **Run the Go backend server**:
   ```bash
   go run ./cmd/server
   # Server runs on http://localhost:8085
   ```

3. **Run the React frontend**:
   ```bash
   cd web
   npm install
   npm run dev
   # Vite dev server runs on http://localhost:3000
   ```

---

## Testing & Quality Expectations

Before submitting any Pull Request, ensure that all test suites and builds pass cleanly:

```bash
# Run Go unit and integration test suite
go test -v ./...

# Build React frontend production bundle
cd web && npm run build

# Validate Docker container build (optional but recommended)
docker build -t chorus-app .
```

---

## Architectural Guidelines

When writing code for Chorus, please keep these core principles in mind:

- **Keep Go Idiomatic & Pragmatic**: Avoid overengineering or adding enterprise abstractions for simple features.
- **Single Source of Truth (SSOT)**: Domain models hold JSON tags. Do not create redundant DTO/mapper layers unless strictly necessary.
- **Concrete Types & Consumer Interfaces**: Return concrete struct pointers from constructors. Define interfaces where they are consumed.
- **Backend as Single Source of Truth**: The frontend must never generate IDs, timestamps, or country determinations. The backend creates all system values.
- **Frontend Design Aesthetics**: Keep the React UI minimal, calm, and distraction-free.

---

## Pull Request Workflow

1. **Issue First**: For non-trivial changes or new features, open an issue first to discuss the approach with maintainers.
2. **Branch Naming**: Use descriptive branch names (e.g., `feat/sse-events`, `fix/rate-limit-headers`, `docs/api-guide`).
3. **Commit Messages**: Follow conventional commits (e.g., `feat(events): add SSE endpoint`, `fix(gitstore): prevent race condition in recovery`).
4. **Linear & Clean History**: Rebase against the latest `main` branch before submitting.
5. **PR Template**: Complete the provided Pull Request template and checklist.
