# 🚀 Quick Start - Deploy to Cloudflare Pages

## Step-by-Step Commands

### 1️⃣ Login to Cloudflare
```bash
npm run cf:login
```
This will open your browser. Login with your Cloudflare account.

### 2️⃣ Verify Login
```bash
npm run cf:whoami
```
You should see your Cloudflare account email.

### 3️⃣ Deploy Your Site
```bash
npm run deploy
```

That's it! 🎉

## What Happens During Deployment?

1. **Builds your React app** → Creates optimized files in `dist` folder
2. **Uploads to Cloudflare** → All your built files go to Cloudflare's edge network
3. **Gets you a URL** → Something like `https://smartappinfo-frontend.pages.dev`

## After First Deployment

Your site will be live at the URL provided. You can:

- ✅ Share the URL with others
- ✅ Connect a custom domain
- ✅ Set up automatic deployments from GitHub

## Connect to GitHub (Recommended)

After your first deployment:

1. Go to https://dash.cloudflare.com
2. Click **Workers & Pages**
3. Find your project
4. Click **Settings** → **Builds & deployments**
5. Click **Connect to Git**
6. Select your repository
7. Set build command: `npm run build`
8. Set build output: `dist`

Now every push to GitHub will auto-deploy! 🚀

## Need Help?

See `CLOUDFLARE_DEPLOYMENT.md` for detailed instructions.
