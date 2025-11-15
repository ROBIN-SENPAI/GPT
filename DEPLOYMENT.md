# Deployment Guide - Senp.AI on GitHub Pages

This guide will help you deploy Senp.AI to GitHub Pages for free hosting.

## 📋 Prerequisites

- A GitHub account
- Git installed on your computer
- Node.js 18+ installed

## 🚀 Step-by-Step Deployment

### Step 1: Create a GitHub Repository

1. Go to [GitHub](https://github.com) and sign in to your account
2. Click the **+** icon in the top right and select **New repository**
3. Name your repository `senpai-gpt` (or any name you prefer)
4. Choose **Public** (required for free GitHub Pages)
5. Click **Create repository**

### Step 2: Initialize Git and Push Code

```bash
# Navigate to your project directory
cd senpai-gpt

# Initialize git (if not already done)
git init

# Add all files
git add .

# Create initial commit
git commit -m "Initial commit: Senp.AI application"

# Add remote repository
git remote add origin https://github.com/YOUR_USERNAME/senpai-gpt.git

# Rename branch to main (if needed)
git branch -M main

# Push to GitHub
git push -u origin main
```

Replace `YOUR_USERNAME` with your actual GitHub username.

### Step 3: Configure GitHub Pages

1. Go to your repository on GitHub
2. Click **Settings** (top right)
3. In the left sidebar, click **Pages**
4. Under **Build and deployment**, select:
   - **Source**: Deploy from a branch
   - **Branch**: `main`
   - **Folder**: `/ (root)`
5. Click **Save**

### Step 4: Enable GitHub Actions

1. Go to your repository
2. Click **Actions** tab
3. GitHub should automatically detect the workflow file
4. The workflow will run automatically on every push to `main`

### Step 5: Verify Deployment

1. After pushing your code, go to the **Actions** tab
2. You should see the "Deploy to GitHub Pages" workflow running
3. Once it completes (green checkmark), your site is live!
4. Your site will be available at: `https://YOUR_USERNAME.github.io/senpai-gpt/`

## 🔧 Configuration for GitHub Pages

### Update vite.config.ts (if needed)

If you named your repository something other than `senpai-gpt`, update the base path:

```typescript
export default defineConfig({
  base: '/repository-name/',
  // ... rest of config
})
```

### Update package.json

Ensure your build script is correct:

```json
{
  "scripts": {
    "build": "vite build",
    "preview": "vite preview"
  }
}
```

## 🌐 Custom Domain (Optional)

To use a custom domain instead of `github.io`:

1. Go to **Settings** → **Pages**
2. Under **Custom domain**, enter your domain name
3. Click **Save**
4. Update your domain's DNS settings to point to GitHub Pages (see GitHub's documentation for your domain provider)

## 📝 Environment Variables

For production, you should use environment variables for API keys:

1. Create a `.env.production` file:
```
VITE_GROQ_API_KEY=your-key-here
VITE_GOOGLE_API_KEY=your-key-here
# ... other keys
```

2. Update `Home.tsx` to use environment variables:
```typescript
const API_KEYS = {
  groq: import.meta.env.VITE_GROQ_API_KEY || 'fallback-key',
  // ... other providers
};
```

3. Add secrets to GitHub:
   - Go to **Settings** → **Secrets and variables** → **Actions**
   - Click **New repository secret**
   - Add each API key as a secret
   - Reference in workflow with `${{ secrets.SECRET_NAME }}`

## 🔄 Automatic Deployment

The included GitHub Actions workflow will:

1. **Trigger** on every push to the `main` branch
2. **Install** dependencies with npm
3. **Build** the project with Vite
4. **Deploy** to GitHub Pages automatically

No manual deployment needed after the initial setup!

## 📊 Monitoring Deployments

1. Go to the **Actions** tab in your repository
2. Click on any workflow run to see details
3. Check logs if deployment fails
4. Common issues:
   - Missing dependencies: Run `npm install` locally
   - Build errors: Check TypeScript errors with `npm run build`
   - API key issues: Verify API keys are valid

## 🚨 Troubleshooting

### Site not appearing after deployment

- Wait 5-10 minutes for GitHub Pages to process
- Clear browser cache (Ctrl+Shift+Delete or Cmd+Shift+Delete)
- Check that the workflow completed successfully in the Actions tab

### 404 errors on subpages

- Ensure your `vite.config.ts` has the correct `base` path
- GitHub Pages requires the base path to match your repository name

### API requests failing

- Check CORS headers from your API providers
- Consider using a backend proxy for production
- Verify API keys are correct and have sufficient quota

### Build fails in GitHub Actions

- Run `npm run build` locally to identify issues
- Check that all dependencies are in `package.json`
- Verify TypeScript configuration is correct

## 📚 Additional Resources

- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [GitHub Actions Documentation](https://docs.github.com/en/actions)
- [Vite Deployment Guide](https://vitejs.dev/guide/static-deploy.html#github-pages)

## ✅ Deployment Checklist

- [ ] GitHub repository created and code pushed
- [ ] GitHub Pages enabled in repository settings
- [ ] Workflow file exists in `.github/workflows/deploy.yml`
- [ ] Build completes successfully locally
- [ ] Site is accessible at `https://YOUR_USERNAME.github.io/senpai-gpt/`
- [ ] All features work correctly on deployed site
- [ ] API keys are configured (demo keys or production keys)
- [ ] Custom domain set up (if applicable)

---

**Your Senp.AI is now live on the internet! 🎉**
