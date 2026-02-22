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

**Trigger:**  
- Pull request author is `dependabot` or `dependabot[bot]`
- Pull request updates a dependency to a secure version

**Analysis Process:**

1. **Identify Dependency Changes**
   - Extract the current dependency version from the PR
   - Extract the target (secure) version dependabot is upgrading to
   - Identify all intermediate versions between current and secure version

2. **Review Release Notes & Changelogs**
   - For each version in the upgrade path, analyze release notes and changelogs
   - Focus specifically on breaking changes including:
     - Removed or renamed methods
     - Removed or renamed classes
     - Changed or removed properties
     - Modified configuration options
     - API changes

3. **Scan Repository for Breaking Changes**
   - Search the entire codebase for references to methods, classes, or properties that will be removed/changed
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
