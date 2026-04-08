# 🚀 Vite + React CI/CD with GitHub Actions

A modern, automated deployment pipeline that builds and deploys a Vite-powered React application to **Vercel** using **GitHub Actions**.


---

## 📖 Overview
This project demonstrates a professional-grade **CI/CD pipeline**. Instead of using a basic "link and deploy" method, I built a custom workflow that gives me full control over how my React application is tested, built, and delivered.
## 🛠️ The Architecture
The pipeline is designed to move the "heavy lifting" from the hosting provider to the source control provider. This mirrors real-world production environments where code must pass through specific gates before going live.

### How it Works:
* **Virtual Runner:** GitHub spins up a fresh Ubuntu container.
* **Tooling:** We install **Node.js** and the **Vercel CLI** from scratch.
* **Authentication:** The runner securely logs into Vercel using encrypted GitHub Secrets.
* **The Prebuilt Strategy:** We use `vercel build` to create a production-ready artifact that includes Vercel's routing metadata, then deploy that specific artifact.

---

## 🌟 Why I Built It This Way
Building a manual pipeline instead of using an automatic one offers several key benefits:

1. **Stability:** By building the project in the GitHub Action, I ensure that the version of Node and the dependencies used for building are exactly what I specify.
2. **Atomic Deploys:** Using the `--prebuilt` flag means the code is only built once. What I see in the logs is exactly what the user sees in the browser.
3. **Future Proofing:** I have already laid the groundwork to add **Vitest** unit tests or **Cypress** E2E tests. If those tests fail, the pipeline will stop, and the live site will remain safe.

---


## 📈 Learning Outcomes
* **DevOps Skills:** Gained hands-on experience with YAML, GitHub Actions, and CLI-based deployment.
* **Troubleshooting:** Successfully debugged permission issues (403 errors), YAML mapping tokens, and dependency conflicts.
* **Scalability:** This setup is industry-standard for professional teams where multiple developers need to push to production safely.

---

> **Final Deployment Result:** Success! View the project on Vercel with a 2-second build time.