#  Step-by-Step Guide to Deploy a Vite React Project on GitHub Pages

Follow these steps to deploy your Vite React project on GitHub Pages.

---

## ✅ 1. Initialize a Git Repository (If Not Already Done)
If your project is not yet linked to GitHub, run:

```sh
git init
git add .
git commit -m "Initial commit"
git branch -M main
git remote add origin https://github.com/your-github-username/your-repo-name.git
git push -u origin main
```
Replace `your-github-username` and `your-repo-name` accordingly.

---

## ✅ 2. Install `gh-pages`
Run the following command inside your project folder:

```sh
npm install gh-pages --save-dev
```

---

## ✅ 3. Update `vite.config.js`
Modify your `vite.config.js` file to set the correct base URL:

```js
import { defineConfig } from 'vite';
import react from '@vitejs/plugin-react';

export default defineConfig({
  base: "/your-repo-name/", // Replace with your GitHub repo name
  plugins: [react()],
});
```

---

## ✅ 4. Update `package.json`
### 1️⃣ Add the `homepage` field:

```json
"homepage": "https://your-github-username.github.io/your-repo-name"
```

### 2️⃣ Modify the `scripts` section:

```json
"scripts": {
  "predeploy": "npm run build",
  "deploy": "gh-pages -d dist"
}
```

---

## ✅ 5. Build and Deploy
### 1️⃣ Build the project:

```sh
npm run build
```
This will generate the `dist/` folder.

### 2️⃣ Deploy to GitHub Pages:

```sh
npm run deploy
```
This will create a new `gh-pages` branch and push only the `dist/` folder.

---

## ✅ 6. Enable GitHub Pages
1. Go to your **GitHub repository**.
2. Click **Settings** > **Pages**.
3. Under **Branch**, select `gh-pages` and save.

Your app will be available at:

```
https://your-github-username.github.io/your-repo-name/
```

---

##  Your Vite React App is Now Live on GitHub Pages!
Let me know if you run into any issues. 

---

##  If `gh-pages` Branch is Not Created Automatically
If `npm run deploy` didn’t create the `gh-pages` branch, follow these steps manually:

### ✅ 1. Verify Existing Branches
Run:
```sh
git branch -r
```
If `origin/gh-pages` is **missing**, the branch wasn’t created.

### ✅ 2. Manually Create and Push the `gh-pages` Branch
#### Step 1: Build the Project
```sh
npm run build
```
#### Step 2: Create the `gh-pages` Branch
```sh
git checkout --orphan gh-pages
```
#### Step 3: Remove All Old Files
```sh
git rm -rf .
```
#### Step 4: Add and Commit the `dist/` Folder
```sh
git add dist
git commit -m "Deploy Vite app to GitHub Pages"
```
#### Step 5: Push to GitHub
```sh
git push origin gh-pages --force
```
This will create and push the `gh-pages` branch to GitHub.

### ✅ 3. Enable GitHub Pages (Again)
1. Go to your **GitHub repository**.
2. Click **Settings** > **Pages**.
3. Under **Branch**, select `gh-pages` and save.

Your app will be available at:

```
https://your-github-username.github.io/your-repo-name/
```

---

 **Your Vite App is Now Live on GitHub Pages!** 

