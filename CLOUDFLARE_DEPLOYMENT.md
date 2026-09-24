# Cloudflare Pages Deployment Guide

This guide will help you deploy your SmartAppInfo frontend to Cloudflare Pages using Wrangler CLI.

## Prerequisites

- Node.js installed
- A Cloudflare account (free tier works fine)
- Wrangler CLI (already installed as dev dependency)

## Step 1: Login to Cloudflare

Run the following command to authenticate with Cloudflare:

```bash
npm run cf:login
```

This will:
- Open your browser
- Ask you to login to Cloudflare
- Grant Wrangler access to your account

To check if you're logged in:
```bash
npm run cf:whoami
```

## Step 2: Build Your Project

Build your project for production:

```bash
npm run build
```

This creates an optimized production build in the `dist` folder.

## Step 3: Deploy to Cloudflare Pages

### First Time Deployment

For your first deployment, run:

```bash
npm run deploy
```

Wrangler will:
1. Ask you to create a new project or select an existing one
2. Upload your `dist` folder contents
3. Deploy to Cloudflare Pages
4. Give you a URL like: `https://smartappinfo-frontend.pages.dev`

### Subsequent Deployments

For production deployments:
```bash
npm run deploy:production
```

For preview deployments (testing):
```bash
npm run deploy
```

## Step 4: Connect to GitHub (Optional but Recommended)

After your first manual deployment, you can connect your repository to GitHub for automatic deployments:

1. Go to [Cloudflare Dashboard](https://dash.cloudflare.com)
2. Navigate to **Workers & Pages** → **Pages**
3. Find your project (smartappinfo-frontend)
4. Click **Settings** → **Builds & deployments**
5. Click **Connect to Git**
6. Select your GitHub repository
7. Configure build settings:
   - **Build command**: `npm run build`
   - **Build output directory**: `dist`
   - **Root directory**: `/frontend` (if in monorepo) or `/` (if separate repo)

## Environment Variables

If you have environment variables in your `.env` file, add them to Cloudflare:

1. Go to your project settings in Cloudflare Dashboard
2. Navigate to **Settings** → **Environment variables**
3. Add your variables for production and preview environments

## Custom Domain (Optional)

To add a custom domain:

1. Go to your project in Cloudflare Dashboard
2. Click **Custom domains**
3. Click **Set up a custom domain**
4. Follow the instructions to add your domain

## Available Commands

| Command | Description |
|---------|-------------|
| `npm run cf:login` | Login to Cloudflare account |
| `npm run cf:logout` | Logout from Cloudflare |
| `npm run cf:whoami` | Check current login status |
| `npm run build` | Build project for production |
| `npm run deploy` | Build and deploy to Cloudflare Pages (preview) |
| `npm run deploy:production` | Build and deploy to production |

## Troubleshooting

### Issue: "Not logged in"
**Solution**: Run `npm run cf:login` to authenticate

### Issue: "Build failed"
**Solution**: Make sure `npm run build` works locally first

### Issue: "Environment variables not working"
**Solution**: Add them in Cloudflare Dashboard under project settings

### Issue: "Deployment taking too long"
**Solution**: Check your internet connection and try again

## Project Configuration

Your project is configured with:
- **Build output directory**: `dist` (where Vite builds your app)
- **Framework**: React + Vite
- **Cloudflare config file**: `wrangler.toml`

## Next Steps

1. ✅ Login to Cloudflare: `npm run cf:login`
2. ✅ Deploy your site: `npm run deploy`
3. ✅ Visit the provided URL to see your live site
4. ✅ (Optional) Connect to GitHub for automatic deployments
5. ✅ (Optional) Add a custom domain

## Resources

- [Cloudflare Pages Documentation](https://developers.cloudflare.com/pages/)
- [Wrangler Documentation](https://developers.cloudflare.com/workers/wrangler/)
- [Deploy React with Cloudflare](https://developers.cloudflare.com/pages/framework-guides/deploy-a-react-site/)
