# Chorus

**Identity belongs to the conversation.**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Go Version](https://img.shields.io/badge/Go-1.22+-00ADD8.svg)](https://go.dev)
[![React](https://img.shields.io/badge/React-18.3-61DAFB.svg)](https://react.dev)
[![Git Persistence Engine](https://img.shields.io/badge/Storage-Native_Git-F05032.svg)](https://git-scm.com)
[![Open Source](https://img.shields.io/badge/Open_Source-%E2%9D%A4-brightgreen.svg)](https://github.com/chorus-project)

Chorus is an open-source anonymous discussion platform where identity is scoped to individual conversations instead of user accounts. It eliminates persistent profile tracking, algorithm-driven feeds, and social media mechanics in favor of thoughtful, chronological discourse.

---

## 🏛️ Ecosystem Overview

The Chorus project is organized into three independent repositories:

### 1. 💬 [Application](https://github.com/chorus-project/chorus) (`chorus`)
- **Live URL:** [chat.joinchorus.app](https://chat.joinchorus.app)
- **Deployment:** Firebase App Hosting
- **Tech Stack:** Go 1.22+, React 18, TypeScript, Vite, TanStack Query
- **Storage:** Audit-proof native Git commit engine (`internal/gitstore`)

### 2. 📖 [Documentation](https://github.com/chorus-project/docs) (`docs`)
- **Live URL:** [docs.joinchorus.app](https://docs.joinchorus.app)
- **Deployment:** Firebase Hosting
- **Tech Stack:** OpenAPI 3.0, Interactive REST API Reference (13 endpoints), SVG Architecture Diagrams, RFCs

### 3. 🌐 [Website](https://github.com/chorus-project/website) (`website`)
- **Live URL:** [joinchorus.app](https://joinchorus.app)
- **Deployment:** Firebase Hosting
- **Tech Stack:** Editorial HTML5/CSS3, Dark/Light Mode, Product Manifesto

---

## 📐 Architecture

```
joinchorus.app (Website)       --> Firebase Hosting     --> website repository
docs.joinchorus.app (Docs)     --> Firebase Hosting     --> docs repository
chat.joinchorus.app (App API)  --> Firebase App Hosting --> chorus repository
```

---

## 🤝 Contributing & Community

Chorus is open source and welcomes contributions! See our contribution guidelines in each repository:
- [Application Contribution Guide](https://github.com/chorus-project/chorus/blob/main/CONTRIBUTING.md)
- [Security Policy](https://github.com/chorus-project/chorus/blob/main/SECURITY.md)

---

## 📄 License

All Chorus repositories are distributed under the [MIT License](LICENSE).
