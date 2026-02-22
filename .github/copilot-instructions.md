# Copilot Instructions for CyberArena Repository

## Repository Summary
**CyberArena** is a comprehensive platform that provides hands-on cybersecurity lab environments fully built and managed on Google Cloud Platform. It enables instructors to deploy custom-built cybersecurity workouts for students with minimal cost by implementing a pay-for-use model where resources are stopped immediately after creation and only started when students actively engage.

## High-Level Repository Information

**Project Type:** Cloud-Native Cybersecurity Training Platform

**Primary Languages:** Python (41%), HTML (26.9%), CSS (12.3%), JavaScript (6.6%)

**Secondary Languages:** Jinja (4.3%), PowerShell (3.1%), Other (5.8%)

**Key Frameworks & Technologies:**
- Google Cloud Platform (Compute Engine, Cloud Functions, Cloud Pub/Sub, Cloud Scheduler, Cloud Storage, Firestore/Datastore)
- Flask (web application framework)
- Python 3.7+ for cloud functions and backend scripts
- Docker/Container technology for containerized applications
- YAML specifications for workout definitions

**Project Structure:**
- **Versions:** The project supports multiple versions - the original version in the root and an in-progress v2 implementation
- **Main Application:** Located in the `main/` directory (Flask-based web application)
- **Cloud Functions:** Located in `cloud-functions/` directory (serverless functions for workout lifecycle management)
- **Build Files:** Located in `build-files/` directory (deployment scripts, server specifications, workout definitions)
- **Admin Scripts:** Located in `admin_scripts/` directory (command-line tools for maintenance and management)
- **Container Applications:** Located in `container-applications/` directory

## Build and Validation Instructions

### Prerequisites
- Python 3.7 or higher
- Google Cloud SDK installed and configured
- A Google Cloud Project with billing enabled
- Domain registration and SSL certificates (for production deployment)

### Bootstrap & Setup

1. **Clone the repository:**
   ```bash
   git clone https://github.com/chancemelby/cyberarena.git
   cd cyberarena

## Copilot Code Review for Dependabot Security Updates

**Purpose:**  
When Copilot is added as a code reviewer to dependabot pull requests, automatically analyze the dependency upgrade for breaking changes that could affect the codebase. Provide developers with clear visibility into whether the security update is safe to merge or requires code changes.

This process applies universally regardless of the programming language (e.g., Python, JavaScript, Java, Go, Ruby, Rust, C#) or package ecosystem (e.g., pip, npm, Maven, Gradle, Go modules, NuGet, Cargo, Composer, RubyGems).

**Trigger:**  
- Pull request author is `dependabot` or `dependabot[bot]`
- Pull request updates a dependency to a secure version

**Analysis Process:**

1. **Identify Dependency Changes**
   - Extract the package name, current version, and target (secure) version from the PR title and description
   - Identify all intermediate versions between current and secure version
   - Determine the package ecosystem from the PR metadata or changed manifest files (e.g., `requirements.txt`, `package.json`, `pom.xml`, `go.mod`, `Cargo.toml`, `*.csproj`)

2. **Review Release Notes & Changelogs**
   - For each version in the upgrade path, analyze release notes and changelogs from the package's official source (PyPI, npm, Maven Central, crates.io, NuGet, pkg.go.dev, etc.)
   - Focus specifically on breaking changes including:
     - Removed or renamed methods, functions, or procedures
     - Removed or renamed classes, types, or interfaces
     - Changed or removed properties, fields, or configuration options
     - Modified function signatures or return types
     - API changes

3. **Scan Repository for Breaking Changes**
   - Search the entire codebase — across all files and all languages present in the repository — for references to methods, classes, types, or properties that will be removed or changed
   - Example: If the upgrade removes `dependency.Calculate()` method, search the repo for all usages of `Calculate()`
   - If found, identify the specific files and line numbers affected

4. **Post Code Review Comment**

   **If breaking changes are detected:**
   ```
   ⚠️ **Breaking Changes Detected in Dependency Upgrade**

   This upgrade includes breaking changes that would affect the codebase:

   **Breaking Change:** [Method/Class/Property Name] has been [removed/renamed/changed]
   
   **Impact:** The following code references would break:
   - [File path and line number]
   - [File path and line number]
   
   **Required Action:** Update the code to use the new method/class/property name or implement an alternative before merging this upgrade.
   
   **Recommended Changes:**
   [Provide specific guidance on how to fix the issue]
   ```

   **If no breaking changes are detected:**
   ```
   ✅ **No Breaking Changes Detected**

   This dependency upgrade to [version] does not introduce any breaking changes to the codebase. Safe to merge.
   ```

5. **Additional Considerations**
   - Flag any deprecated warnings in the changelog (not breaking changes, but worth noting)
   - If major version upgrades occur, provide extra scrutiny
   - Include links to the official release notes or changelog for developer reference
