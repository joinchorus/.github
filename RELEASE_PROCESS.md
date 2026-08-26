# Chorus Release Process & Maintainer Guide

This document outlines the standard release process for Chorus maintainers. Following this guide ensures reproducible, well-documented, and production-grade software releases.

---

## Release Checklist Overview

1. [Pre-Release Audit](#1-pre-release-audit)
2. [Version Bump Protocol](#2-version-bump-protocol)
3. [Test & Build Verification](#3-test--build-verification)
4. [Changelog & Documentation Updates](#4-changelog--documentation-updates)
5. [Git Tag & Release Commit](#5-git-tag--release-commit)
6. [GitHub Release Creation](#6-github-release-creation)
7. [Post-Release Verification](#7-post-release-verification)

---

## 1. Pre-Release Audit

Before preparing a release, ensure all features merged into `main` comply with project standards:
- **Code Standards**: Zero warnings from `go vet ./...` and `npm run build`.
- **Security Check**: Verify security headers, CSP compatibility, and authentication handlers.
- **Commit History**: Ensure commits follow Conventional Commits and atomic staging.

---

## 2. Version Bump Protocol

Chorus follows [Semantic Versioning 2.0.0](https://semver.org/).

1. Identify version increment:
   - **MAJOR**: Breaking API or architectural changes.
   - **MINOR**: Backward-compatible new features.
   - **PATCH**: Backward-compatible bug fixes or security patches.
   - **PRE-RELEASE**: Append `-alpha` or `-beta` suffix (e.g., `v0.1.0-alpha`).

2. Update version strings in:
   - `web/package.json` (`"version": "0.1.0-alpha"`)
   - `docs/public/openapi.yaml` (`info.version: "0.1.0-alpha"`)
   - `internal/config/config.go` (`AppVersion = "0.1.0-alpha"`)

---

## 3. Test & Build Verification

Run the full verification suite across all packages:

```bash
# 1. Backend Go Test Suite
cd chorus
go test -v ./...

# 2. Frontend React Build & Type Check
cd web
npm run build
```

Both commands **must** return exit code `0` before proceeding.

---

## 4. Changelog & Documentation Updates

1. Update `CHANGELOG.md` following [Keep a Changelog](https://keepachangelog.com/):
   - Categorize entries into: `Added`, `Changed`, `Deprecated`, `Removed`, `Fixed`, `Security`.

2. Update `docs/DEPLOYMENT.md` if deployment configurations or environment variables changed.

---

## 5. Git Tag & Release Commit

1. Create a release commit:
   ```bash
   git add CHANGELOG.md docs/ web/package.json internal/
   git commit -m "chore(release): prepare v0.1.0-alpha release"
   ```

2. Create an annotated Git tag with release highlights:
   ```bash
   git tag -a v0.1.0-alpha -m "v0.1.0-alpha

   First public alpha release.

   Highlights:
   - production runtime
   - moderation authentication
   - rate limiting
   - request correlation
   - graceful shutdown
   - modern HTTP security

   See CHANGELOG.md for details."
   ```

3. Push commits and tags to remote:
   ```bash
   git push origin main
   git push origin v0.1.0-alpha
   ```

---

## 6. GitHub Release Creation

1. Navigate to GitHub repository Releases section.
2. Draft a new release selecting tag `v0.1.0-alpha`.
3. Paste official Release Notes.
4. Publish release.

---

## 7. Post-Release Verification

1. Verify live deployment endpoint (`/healthz`).
2. Verify production static bundle serving.
3. Close corresponding milestone in GitHub issues.
4. Open next milestone (e.g. `v0.2.0-beta`).
