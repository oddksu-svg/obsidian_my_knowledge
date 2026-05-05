# Setup Guide & Prerequisites

Before starting the AI & Machine Learning Engineering Course, please ensure you have completed the following prerequisites:

## 1. Install Gemini CLI
- Required for interacting with the AI assistant from your terminal.
- Follow the official documentation to install and authenticate the **Gemini CLI** on your system.

## 2. Sign Up for GitHub
- Required for version control, collaboration, and hosting your code repositories.
- Go to [GitHub](https://github.com/) and create a free account.
- *Related:* [[Phase 1 - Foundations & Classical Machine Learning]] (Week 1 covers Git Version Control).

## 3. Sign Up for Vercel
- Required for deploying web applications, APIs, and sharing your projects later in the course.
- Go to [Vercel](https://vercel.com/) and sign up. It is highly recommended to sign up using your GitHub account for seamless integration.

## 4. Install Obsidian
- Required for viewing, managing, and navigating this knowledge base efficiently.
- Download and install Obsidian from [obsidian.md](https://obsidian.md/).
- Open this folder as a Vault in Obsidian to enable internal linking and tag support.

## 5. Install & Setup Quartz (For Publishing)
- Required to publish this Obsidian vault online for free.
- **Prerequisites:** Ensure you have Node.js (`npm`) and Git installed.
- **Steps:**
  1. Clone Quartz: `git clone https://github.com/jackyzha0/quartz.git quartz_site`
  2. Navigate and clean up: `cd quartz_site`, delete `.git` and `content/*`.
  3. Copy your Obsidian vault contents into `quartz_site/content`.
  4. Install dependencies: `npm install`.
  5. Test locally: `npx quartz build --serve` (view at http://localhost:8080).
  6. Deploy: Initialize Git, push to GitHub, and link the repository to Vercel.

---
Back to [[Course Overview]]

#tags #setup #prerequisites #tools
