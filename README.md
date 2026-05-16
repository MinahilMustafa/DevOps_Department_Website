# Computer Science Department Website - DevOps Pipeline

This project is a complete end-to-end DevOps pipeline for the University Computer Science Department static website. It was developed to demonstrate containerization, Continuous Integration (CI), Continuous Deployment (CD), and Git Flow branching strategies.

## Project Architecture

1. **Web Pages (HTML/CSS):** Premium, modern, responsive static web pages (`index.html`, `courses.html`, `faculty.html`, `admissions.html`, `contact.html`).
2. **Containerization (Docker):** The application is fully containerized using a minimal `nginx:alpine` image.
3. **Branching Strategy (Git Flow):**
   - `main` / `master`: Production-ready code.
   - `release`: Staging / QA testing environment.
   - `develop`: Active development and feature integration.
4. **CI/CD Pipelines (GitHub Actions):**
   - **CI Pipeline:** Automatically lints HTML/CSS and tests the Docker image build on all pushes and Pull Requests.
   - **CD Pipeline:** Automatically deploys to Vercel (Development, Staging, and Production environments) based on branch activity, securely utilizing GitHub Environments and Secrets.

## Setup & Local Development

To run this website locally using Docker:

1. Clone the repository.
2. Build the Docker image:
   ```bash
   docker build -t cs-dept-website .
   ```
3. Run the Docker container:
   ```bash
   docker run -d -p 8080:80 cs-dept-website
   ```
4. Open your browser and navigate to `http://localhost:8080`.

## Deployment Environments

* **Development:** Deployed from the `develop` branch.
* **Staging/QA:** Deployed from the `release` branch.
* **Production:** Deployed from the `main` branch.

*All deployment secrets (Vercel IDs and Tokens) are securely managed via GitHub Environments.*
