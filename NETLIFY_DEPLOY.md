# Deploy WikiFruity to Netlify

This guide will help you deploy WikiFruity to Netlify with password protection.

## Prerequisites

- GitHub account with access to this repository
- Netlify account (free) - [Sign up here](https://app.netlify.com/signup)

## Deployment Steps

### 1. Connect Your Repository to Netlify

1. Go to [Netlify](https://app.netlify.com/)
2. Click **"Add new site"** → **"Import an existing project"**
3. Choose **"GitHub"** as your Git provider
4. Authorize Netlify to access your GitHub account
5. Select the **`fruity-ai/wikifruity`** repository

### 2. Configure Build Settings

Netlify should auto-detect the settings from `netlify.toml`, but verify:

- **Base directory**: (leave empty)
- **Build command**: `pip install -r requirements.txt && mkdocs build`
- **Publish directory**: `site`

Click **"Deploy site"**

### 3. Enable Password Protection

Once deployed:

1. Go to your site's **Settings** → **Access & security** → **Visitor access**
2. Select **"Password protect this site"**
3. Enter password: `Marmalade!`
4. Click **"Save"**

That's it! Your site is now password protected.

## Custom Domain (Optional)

To use a custom domain:

1. Go to **Domain settings** → **Add custom domain**
2. Follow the instructions to configure DNS
3. Netlify provides free HTTPS/SSL certificates

## Environment Variables (If Needed)

If you need to set environment variables:

1. Go to **Site settings** → **Environment variables**
2. Click **"Add a variable"**
3. Add your key-value pairs

## Continuous Deployment

Netlify automatically deploys when you push to your main branch:

- Push to `main` → Automatic deployment
- Pull requests → Deploy previews (optional)

## Build Status Badge

Add this to your README.md to show build status:

```markdown
[![Netlify Status](https://api.netlify.com/api/v1/badges/YOUR-SITE-ID/deploy-status)](https://app.netlify.com/sites/YOUR-SITE-NAME/deploys)
```

## Troubleshooting

### Build Fails

- Check the build logs in Netlify dashboard
- Verify all dependencies are in `requirements.txt`
- Ensure Python version matches (3.9)

### Site Not Updating

- Check recent deployments in Netlify dashboard
- Force a new deploy: **Deploys** → **Trigger deploy** → **Clear cache and deploy site**

### Password Not Working

- Go to **Site settings** → **Access & security**
- Verify password protection is enabled
- Re-enter the password and save

## Cost

Free tier includes:
- 100 GB bandwidth/month
- Unlimited sites
- Password protection
- HTTPS
- Continuous deployment

## Support

- [Netlify Documentation](https://docs.netlify.com/)
- [Netlify Community Forum](https://answers.netlify.com/)
- [Contact Netlify Support](https://www.netlify.com/support/)

## Alternative: Keep GitHub Pages

If you prefer to stick with GitHub Pages:
- Make the repository private (requires GitHub Pro)
- Or keep it public without password protection
