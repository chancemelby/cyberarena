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

## Dependabot Pull Requests Reviews

- When dependabot is the author of a pull request
- Check the current version of the dependency
- Check the secure version of the dependency
- Check the versions in between the current version and secure version of dependecy
- Analyze release notes and changelog for each version checked
- Identify any changes with methods, classes, or property names
- Example: Current Version - dependency.Calculate() works - Version Update - Calculate() is removed
- Check the repository for any reference to deprecated or changed methods, classes, or property names
- Comment on code review any breaking changes that would affect the upgrade to secure version
- If no breaking changes are identified, state that
  
