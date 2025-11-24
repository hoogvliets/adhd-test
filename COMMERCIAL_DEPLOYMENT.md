# Commercial ADHD Test - Netlify Deployment Guide

Complete guide to deploying your commercial ADHD screening test to Netlify and setting up monetization.

## 📋 Table of Contents

1. [Prerequisites](#prerequisites)
2. [Deploy to Netlify](#deploy-to-netlify)
3. [Set Up Google AdSense](#set-up-google-adsense)
4. [Configure Google Analytics](#configure-google-analytics)
5. [Custom Domain Setup](#custom-domain-setup)
6. [SEO Optimization](#seo-optimization)
7. [Monitoring & Analytics](#monitoring--analytics)

---

## Prerequisites

- GitHub account
- Netlify account (free) - [Sign up here](https://app.netlify.com/signup)
- Google account (for AdSense and Analytics)
- Your code pushed to GitHub

---

## Deploy to Netlify

### Step 1: Push Code to GitHub

```bash
cd /Users/raphaelh/code/tinkering/adhd-test

# Make sure you're on the commercial-site branch
git status

# Add all files
git add .

# Commit changes
git commit -m "Commercial version with ads and SEO"

# Push to GitHub (create repo first if needed)
git push origin commercial-site
```

### Step 2: Connect to Netlify

1. Go to [Netlify](https://app.netlify.com)
2. Click **"Add new site"** → **"Import an existing project"**
3. Choose **"Deploy with GitHub"**
4. Authorize Netlify to access your GitHub account
5. Select your repository
6. Configure build settings:
   - **Branch to deploy:** `commercial-site`
   - **Build command:** (leave empty)
   - **Publish directory:** `.` (root)
7. Click **"Deploy site"**

### Step 3: Your Site is Live! 🎉

Netlify will assign you a random URL like: `https://random-name-123456.netlify.app`

Your site is now live and accessible!

---

## Set Up Google AdSense

### Step 1: Apply for AdSense

1. Go to [Google AdSense](https://www.google.com/adsense)
2. Click **"Get Started"**
3. Enter your website URL (your Netlify URL)
4. Fill out the application form
5. Add your payment information

**Note:** Approval typically takes 1-2 weeks. Google will review your site for:
- Original content
- Sufficient content
- Compliance with policies
- User experience

### Step 2: Get Your AdSense Code

Once approved:

1. Log in to AdSense
2. Go to **Ads** → **Overview**
3. Click **"By ad unit"**
4. Create ad units:
   - **Display ad** (728x90) for header banner
   - **Display ad** (300x250) for sidebar and results
   - **Display ad** (300x600) for sidebar

5. Copy the ad codes

### Step 3: Update Your Site

Replace the placeholder codes in `index.html`:

**Find this:**
```html
data-ad-client="ca-pub-XXXXXXXXXXXXXXXX"
data-ad-slot="XXXXXXXXXX"
```

**Replace with your actual codes:**
```html
data-ad-client="ca-pub-1234567890123456"  <!-- Your publisher ID -->
data-ad-slot="9876543210"  <!-- Your ad slot ID -->
```

**Also update the AdSense script in the `<head>`:**
```html
<script async src="https://pagead2.googlesyndication.com/pagead/js/adsbygoogle.js?client=ca-pub-1234567890123456"
     crossorigin="anonymous"></script>
```

### Step 4: Deploy Updates

```bash
git add index.html
git commit -m "Add AdSense codes"
git push origin commercial-site
```

Netlify will automatically redeploy (takes ~1 minute).

---

## Configure Google Analytics

### Step 1: Create Analytics Property

1. Go to [Google Analytics](https://analytics.google.com)
2. Click **"Admin"** (bottom left)
3. Click **"Create Property"**
4. Enter property details:
   - Property name: "ADHD Screening Test"
   - Timezone and currency
5. Click **"Next"** and complete setup
6. Choose **"Web"** platform
7. Enter your website URL

### Step 2: Get Tracking ID

1. After creating property, go to **Admin** → **Data Streams**
2. Click your web stream
3. Copy your **Measurement ID** (format: `G-XXXXXXXXXX`)

### Step 3: Update Your Site

In `index.html`, replace:

```html
<script async src="https://www.googletagmanager.com/gtag/js?id=G-XXXXXXXXXX"></script>
<script>
    window.dataLayer = window.dataLayer || [];
    function gtag(){dataLayer.push(arguments);}
    gtag('js', new Date());
    gtag('config', 'G-XXXXXXXXXX');  <!-- Replace with your ID -->
</script>
```

### Step 4: Deploy

```bash
git add index.html
git commit -m "Add Google Analytics tracking"
git push origin commercial-site
```

---

## Custom Domain Setup

### Option 1: Buy a Domain

Recommended registrars:
- **Namecheap** (~$10/year for .com)
- **Google Domains** (~$12/year)
- **Cloudflare** (~$10/year)

Good domain ideas:
- `adhdtest.com`
- `adhdscreening.com`
- `adhdcheck.com`
- `quickadhdtest.com`

### Option 2: Configure Domain in Netlify

1. In Netlify, go to **Site settings** → **Domain management**
2. Click **"Add custom domain"**
3. Enter your domain (e.g., `adhdtest.com`)
4. Netlify will provide DNS records

### Option 3: Update DNS

At your domain registrar, add these DNS records:

**For root domain (adhdtest.com):**
- Type: `A`
- Name: `@`
- Value: `75.2.60.5` (Netlify's IP)

**For www subdomain:**
- Type: `CNAME`
- Name: `www`
- Value: `your-site.netlify.app`

**Wait 24-48 hours for DNS propagation.**

### Option 4: Enable HTTPS

Netlify automatically provides free SSL certificates. Once DNS is configured:

1. Go to **Domain settings** → **HTTPS**
2. Click **"Verify DNS configuration"**
3. Click **"Provision certificate"**

Your site will now be accessible via `https://yourdomain.com`!

---

## SEO Optimization

### Update Site URLs

In these files, replace `https://yoursite.com` with your actual domain:

1. **index.html** - Open Graph meta tags
2. **sitemap.xml** - All `<loc>` tags
3. **robots.txt** - Sitemap URL
4. **netlify.toml** - Redirect rules

### Submit to Search Engines

#### Google Search Console

1. Go to [Google Search Console](https://search.google.com/search-console)
2. Click **"Add property"**
3. Enter your domain
4. Verify ownership (Netlify makes this easy)
5. Submit your sitemap: `https://yourdomain.com/sitemap.xml`

#### Bing Webmaster Tools

1. Go to [Bing Webmaster Tools](https://www.bing.com/webmasters)
2. Add your site
3. Import from Google Search Console (easiest)
4. Submit sitemap

### Create Content for SEO

To drive organic traffic, consider adding:

1. **Blog posts** about ADHD (create `/blog/` folder)
2. **FAQ page** answering common ADHD questions
3. **Resources page** linking to ADHD organizations
4. **About page** explaining the test

More content = more keywords = more traffic = more ad revenue!

---

## Monitoring & Analytics

### Track Your Metrics

**Google Analytics Dashboard:**
- Daily visitors
- Page views
- Bounce rate
- Average session duration
- Traffic sources

**Google AdSense Dashboard:**
- Ad impressions
- Click-through rate (CTR)
- Earnings per click (EPC)
- Revenue

### Revenue Expectations

Based on typical AdSense performance for health/medical content:

| Daily Visitors | Monthly Revenue (Estimate) |
|----------------|---------------------------|
| 100            | $3 - $15                  |
| 500            | $15 - $75                 |
| 1,000          | $30 - $150                |
| 5,000          | $150 - $750               |
| 10,000         | $300 - $1,500             |

*Note: Actual revenue varies based on traffic quality, ad placement, and niche competition*

### Optimization Tips

1. **Improve CTR:**
   - Test different ad placements
   - Use responsive ad units
   - Match ad colors to site design

2. **Increase Traffic:**
   - Write SEO-optimized blog posts
   - Share on social media
   - Build backlinks from ADHD communities
   - Answer ADHD questions on Reddit/Quora with link to test

3. **Improve User Experience:**
   - Fast loading times (Netlify CDN helps!)
   - Mobile-friendly design
   - Clear call-to-actions
   - Valuable content

---

## Troubleshooting

### Ads Not Showing

- **AdSense not approved yet?** Ads won't show until approval
- **Ad blocker enabled?** Disable to test
- **Wrong ad codes?** Double-check publisher ID and slot IDs
- **Need to wait:** New ads can take 10-20 minutes to appear

### Analytics Not Tracking

- **Wrong tracking ID?** Verify in Google Analytics
- **Browser extensions blocking?** Test in incognito mode
- **Just deployed?** Wait 24 hours for data to appear

### Site Not Loading

- **DNS not propagated?** Can take up to 48 hours
- **Netlify build failed?** Check deploy logs in Netlify dashboard
- **Wrong branch?** Ensure `commercial-site` branch is selected

---

## Next Steps

1. ✅ Deploy to Netlify
2. ✅ Apply for Google AdSense
3. ✅ Set up Google Analytics
4. ⏳ Wait for AdSense approval (1-2 weeks)
5. ⏳ Add AdSense codes once approved
6. 🎯 Drive traffic through SEO and content marketing
7. 💰 Start earning passive income!

---

## Support Resources

- [Netlify Documentation](https://docs.netlify.com)
- [Google AdSense Help](https://support.google.com/adsense)
- [Google Analytics Help](https://support.google.com/analytics)
- [SEO Starter Guide](https://developers.google.com/search/docs/beginner/seo-starter-guide)

---

**Good luck with your commercial ADHD test site!** 🚀

Remember: The key to success is consistent traffic. Focus on SEO and creating valuable content to drive visitors to your site.
