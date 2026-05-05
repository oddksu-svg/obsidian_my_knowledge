# Quartz Deployment Guide: Obsidian to Vercel

This guide provides a comprehensive, step-by-step walkthrough on how to take your local Obsidian Vault and publish it as a public website using Quartz, GitHub, and Vercel.

## Phase 1: Local Setup

### 1. Install Prerequisites
Make sure you have the following installed on your computer:
- **Git:** For version control.
- **Node.js (npm):** To run and build Quartz.
- **Obsidian:** To write your markdown notes.

### 2. Clone Quartz
Open your terminal and clone the official Quartz repository into a new folder (e.g., `quartz_site`).
```bash
git clone https://github.com/jackyzha0/quartz.git quartz_site
cd quartz_site
```

### 3. Clean the Default Quartz Repository
You need to remove the default git history and default content provided by Quartz so you can start fresh.
```bash
# Windows (PowerShell)
Remove-Item -Recurse -Force .git
Remove-Item -Recurse -Force content\*

# Mac/Linux
rm -rf .git
rm -rf content/*
```

### 4. Import Your Obsidian Vault
Copy all the files and folders from your existing Obsidian vault into the `quartz_site/content` folder.
*Note: Do not copy the `.obsidian` hidden folder.*

### 5. Install Dependencies and Test Locally
Install the required Node.js packages and start the local development server to preview your site.
```bash
npm install
npx quartz build --serve
```
Open `http://localhost:8080` in your web browser. You should see your Obsidian notes rendered as a website!

---

## Phase 2: GitHub Integration

### 1. Create a GitHub Repository
1. Go to [GitHub](https://github.com/new).
2. Create a new repository (e.g., `obsidian-public-vault`).
3. **Important:** Leave it completely empty. Do not check "Add a README file" or "Add .gitignore".

### 2. Initialize Git Locally
Go back to your terminal (inside the `quartz_site` folder) and initialize your own Git repository.
```bash
git init
git add .
git commit -m "Initial Obsidian vault commit"
```

### 3. Push to GitHub
Link your local repository to the GitHub repository you just created and push the code.
```bash
git remote add origin https://github.com/YOUR-USERNAME/obsidian-public-vault.git
git branch -M main
git push -u origin main
```

---

## Phase 3: Vercel Deployment

### 1. Prepare Vercel Configuration
To ensure Vercel routes your pages correctly without requiring `.html` extensions, create a file named `vercel.json` in the root of your `quartz_site` folder:
```json
{
  "cleanUrls": true
}
```

Also, ensure your `package.json` has a build script. Quartz v4 requires this to be manually added for Vercel:
```json
  "scripts": {
    "build": "npx quartz build",
    ...
  }
```
Commit and push these changes to GitHub.

### 2. Import to Vercel
1. Log in to your [Vercel Dashboard](https://vercel.com/dashboard).
2. Click **Add New... > Project**.
3. Locate your GitHub repository and click **Import**.
4. Leave the Framework Preset as **Other**.
5. The Build Command should default to `npm run build`.
6. Click **Deploy**.

### 3. Disable Deployment Protection (Optional but Recommended)
If Vercel asks for a login when you visit the site (showing an "Authenticated" screen), it means Deployment Protection is on.
1. In your Vercel project, go to **Settings > Deployment Protection**.
2. Find the **Vercel Authentication** section.
3. Toggle it to **Disabled**.
4. Click **Save**.

---

## Phase 4: Updating Your Site

Whenever you add new notes or edit existing ones in Obsidian:
1. Copy the updated files into `quartz_site/content`.
2. Open your terminal in `quartz_site`.
3. Run the following commands:
```bash
git add .
git commit -m "Update notes"
git push
```
Vercel will detect the push to GitHub, automatically rebuild your site, and deploy the new version within a minute!

#tags #deployment #vercel #github #quartz
