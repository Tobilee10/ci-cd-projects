# **CI/CD Static Website Deployment Pipeline**

A automated CI/CD pipeline designed to validate and deploy a static web application to GitHub Pages using GitHub Actions. Every push to the main branch triggers automated quality checks before shipping the updated site to production.
🚀 Live Demo


### 🛠️ Tech Stack & Tools

- [x] Frontend: HTML5, CSS3
- [x] CI/CD Automation: GitHub Actions
- [x] Hosting Platform: GitHub Pages
- [x] Environment: Linux (Ubuntu Latest Runner)

    

### 📁 Repository Structure

```
ci-cd-projects/
├── .github/
│   └── workflows/
│       └── deploy.yml              # GitHub Actions pipeline configuration
└── dockerised-static-webiste-pipeline/
    ├── index.html                  # Main website landing page
    └── styles.css                  # Core application stylesheets
```

### ⚙️ CI/CD Pipeline Workflow

The automation pipeline defined in .github/workflows/deploy.yml breaks down into two distinct stages:
1. Validation Stage (validate)

    Environment: ubuntu-latest

    Actions: * Checks out the latest codebase.

        Navigates into the project directory (./dockerised-static-webiste-pipeline).

        Runs shell assertions to ensure crucial production assets (index.html and styles.css) exist. If any file is missing, the pipeline breaks safely before deployment.

2. Deployment Stage (deploy)

    Environment: ubuntu-latest

    Dependency: Blocks execution until the validate job passes successfully.

    Actions:

        Packages the static application files from the target subdirectory.

        Directs GitHub's deployment engine to securely serve the subfolder as the primary root index for the production URL.

### 💻 Local Development Setup

To run and view this project locally on your system:

    Clone the repository:
    Bash

    git clone https://github.com/tobilee10/ci-cd-projects.git
    cd ci-cd-projects

    Navigate to the web project directory:
    Bash

    cd dockerised-static-webiste-pipeline

    Launch the site:

        Open index.html directly in your preferred web browser.

        Or use a local development server (such as VS Code's Live Server extension or Python's built-in module):
        Bash

        python3 -m http.server 8000

        Then navigate to http://localhost:8000.

### 🔒 Configuration Notes

To ensure the pipeline executes successfully in a fork or secondary environment, ensure the following project permissions are set:

    In your GitHub repository, navigate to Settings > Pages.

    Under Build and deployment, switch the Source dropdown selection to GitHub Actions.