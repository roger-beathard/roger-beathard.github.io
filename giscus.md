# Giscus Setup Guide

## Step 1: Prepare Your GitHub Repository

1. **Create/Use a public GitHub repository** for your Hugo site
2. **Enable GitHub Discussions** in your repo:
   - Go to your repo on GitHub
   - Click Settings tab
   - Scroll down to "Features" section
   - Check "Discussions"

## Step 2: Install Giscus App

1. Go to [giscus.app](https://giscus.app/)
2. **Install the Giscus app** on your repository:
   - Click "configuration" link
   - Select your repository
   - Grant permissions

## Step 3: Get Your Configuration Values

1. Go back to [giscus.app](https://giscus.app/)
2. **Fill out the form**:
   - Repository: `your-username/your-repo-name`
   - Page ↔️ Discussions Mapping: Choose "Discussion title contains page pathname"
   - Discussion Category: Choose "General" (or create a "Comments" category)
3. **Copy the generated values**:
   - `data-repo-id`
   - `data-category-id`

## Step 4: Update Your Hugo Config

Replace these values in your `config.toml`:

```toml
[params.giscus]
enabled = true
repo = "your-username/your-repo-name"        # Your actual repo
repo_id = "R_kgDOxxxxxxx"                   # From giscus.app
category = "General"                         # Your chosen category  
category_id = "DIC_kwDOxxxxxxx"             # From giscus.app
```

## Step 5: Test Comments

1. **Deploy your site** (or run `hugo server` locally with `--bind 0.0.0.0` if testing locally)
2. **Visit a blog post** - you should see the comments section at the bottom
3. **Post a test comment** - it will appear as a GitHub Discussion in your repo

## Optional: Disable Comments on Specific Posts

Add this to any post's front matter to disable comments:

```yaml
---
title: "My Post"
disable_comments: true
---
```

## Features Included:

✅ Comments appear on all blog posts  
✅ GitHub authentication required (reduces spam)  
✅ Reactions/upvotes enabled  
✅ Mobile responsive  
✅ Light theme (matches your site)  
✅ Easy moderation through GitHub  
✅ SEO friendly  

## Moderation

- **View comments**: Go to your repo → Discussions tab
- **Moderate**: Use GitHub's discussion moderation tools
- **Delete spam**: Delete discussions in GitHub
- **Lock discussions**: Prevent further comments if needed

That's it! Your blog now has a professional commenting system powered by GitHub.
