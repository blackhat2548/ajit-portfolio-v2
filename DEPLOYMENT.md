# Quick Deployment Guide 🚀

Follow these steps to get your portfolio live on GitHub Pages in minutes!

## Prerequisites
- GitHub account
- Git installed on your computer

## Step-by-Step Deployment

### 1. Upload to GitHub

```bash
# Navigate to the portfolio-website folder
cd portfolio-website

# Initialize git repository
git init

# Add all files
git add .

# Commit files
git commit -m "Initial portfolio commit"

# Create main branch
git branch -M main

# Add remote repository (replace YOUR_USERNAME)
git remote add origin https://github.com/Ajitmalik18/portfolio-website.git

# Push to GitHub
git push -u origin main
```

### 2. Enable GitHub Pages

1. Go to your repository on GitHub: `https://github.com/Ajitmalik18/portfolio-website`
2. Click on **"Settings"** tab
3. Scroll down and click **"Pages"** in the left sidebar
4. Under **"Source"**, select:
   - Branch: `main`
   - Folder: `/ (root)`
5. Click **"Save"**
6. Wait 2-3 minutes for deployment
7. Your site will be live at: `https://ajitmalik18.github.io/portfolio-website/`

### 3. Set Up Contact Form (IMPORTANT!)

Before the contact form works, you MUST set up EmailJS:

1. Read `EMAILJS_SETUP.md` for detailed instructions
2. Quick setup:
   - Go to [EmailJS.com](https://www.emailjs.com/)
   - Create free account
   - Connect Gmail
   - Create email template
   - Get: Public Key, Service ID, Template ID
   - Update `js/script.js` with your keys

### 4. Test Your Site

1. Visit: `https://ajitmalik18.github.io/portfolio-website/`
2. Check all sections load correctly
3. Test contact form
4. Verify email delivery

## Alternative Hosting Options

### Netlify (Recommended for beginners)

1. Go to [Netlify.com](https://www.netlify.com/)
2. Sign up with GitHub
3. Click "Add new site" → "Import an existing project"
4. Choose your GitHub repository
5. Click "Deploy"
6. Your site is live instantly!

### Vercel

1. Go to [Vercel.com](https://vercel.com/)
2. Sign up with GitHub
3. Click "New Project"
4. Import your repository
5. Click "Deploy"

## Custom Domain (Optional)

### If you have your own domain:

**GitHub Pages:**
1. Add a file named `CNAME` in root directory
2. Add your domain: `yourname.com`
3. Configure DNS in your domain registrar:
   - Type: `A`
   - Name: `@`
   - Value: `185.199.108.153` (and other GitHub IPs)

**Netlify/Vercel:**
1. Go to domain settings in dashboard
2. Add custom domain
3. Follow DNS configuration instructions

## Updating Your Site

After making changes:

```bash
git add .
git commit -m "Updated portfolio"
git push
```

GitHub Pages/Netlify/Vercel will auto-deploy in 1-2 minutes.

## Troubleshooting

### Site not loading?
- Wait 5 minutes after first deploy
- Check GitHub Actions tab for build status
- Ensure index.html is in root directory

### Contact form not working?
- Check browser console (F12) for errors
- Verify EmailJS setup is complete
- Test EmailJS template in their dashboard

### Styles not loading?
- Check that CSS and JS paths are correct
- Clear browser cache (Ctrl+F5)
- Check file names match (case-sensitive)

## Need Help?

- GitHub Pages docs: [docs.github.com/pages](https://docs.github.com/pages)
- EmailJS support: [emailjs.com/docs](https://www.emailjs.com/docs/)
- Contact me: ajitmalik0018@gmail.com

## Summary Checklist

- [ ] Files uploaded to GitHub
- [ ] GitHub Pages enabled
- [ ] EmailJS account created
- [ ] Email service connected
- [ ] Template created
- [ ] Keys added to script.js
- [ ] Site tested and working
- [ ] Contact form tested
- [ ] Shared portfolio link

Your portfolio is now live! 🎉
