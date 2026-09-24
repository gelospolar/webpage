# GitHub Pages Setup for Gelos Polar

Your landing page is ready to deploy to GitHub Pages. Follow these steps:

## Step 1: Create a GitHub Repository

1. Go to https://github.com/new
2. **Repository name:** `gelospolar.github.io` (replace `gelospolar` with your GitHub username)
   - This exact naming is required for GitHub Pages to work automatically
3. **Description:** "Gelos Polar - Landing page"
4. **Public** (required for free GitHub Pages)
5. **Do NOT initialize with README, .gitignore, or license** (you already have commits locally)
6. Click **Create repository**

## Step 2: Connect Local Repo to GitHub

After creating the repo, GitHub will show you commands. Run these in your terminal (in `C:\Users\alexl\folder\polar`):

```bash
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/gelospolar.github.io.git
git push -u origin main
```

Replace `YOUR_USERNAME` with your actual GitHub username.

**If you get a permission error:** GitHub now requires a Personal Access Token instead of your password. 
- Go to https://github.com/settings/tokens
- Click "Generate new token (classic)"
- Check `repo` scope
- Copy the token
- When prompted for password, paste the token instead

## Step 3: Enable GitHub Pages

1. Go to your repo: `https://github.com/YOUR_USERNAME/gelospolar.github.io`
2. Click **Settings** (top right)
3. Scroll left sidebar to **Pages**
4. Under "Build and deployment":
   - **Source:** Select "Deploy from a branch"
   - **Branch:** Select `main` and `/root`
   - Click **Save**

Your site will be live at: **https://YOUR_USERNAME.github.io**

## Step 4: Add a Custom Domain (Optional)

If you buy a domain (e.g., `gelospolar.com.br` from Registro.br):

1. In **Settings > Pages**, under "Custom domain", enter your domain name
2. Click **Save**
3. GitHub will create a `CNAME` file automatically
4. Go to your domain registrar (Registro.br, Namecheap, etc.)
5. Update DNS records to point to GitHub:
   - **For apex domain** (`gelospolar.com.br`): Add an `A` record pointing to GitHub's IPs:
     ```
     185.199.108.153
     185.199.109.153
     185.199.110.153
     185.199.111.153
     ```
   - **For www subdomain** (`www.gelospolar.com.br`): Add a `CNAME` record pointing to `YOUR_USERNAME.github.io`

6. Wait 5–30 minutes for DNS to propagate
7. GitHub will auto-enable HTTPS once DNS is verified

## Step 5: Update Your Landing Page

To make changes:

1. Edit `index.html` locally
2. Commit and push:
   ```bash
   git add index.html
   git commit -m "Update WhatsApp number and photos"
   git push
   ```
3. Changes appear on your live site within seconds

## Quick Checklist

- [ ] Created GitHub account (if needed)
- [ ] Created `gelospolar.github.io` repo
- [ ] Ran `git remote add origin` and `git push`
- [ ] Enabled GitHub Pages in Settings
- [ ] Site is live at `https://YOUR_USERNAME.github.io`
- [ ] (Optional) Bought custom domain and updated DNS

## Troubleshooting

**Site shows 404:**
- Wait 2–3 minutes after enabling Pages
- Check that branch is set to `main` and folder is `/root`
- Verify `index.html` is in the repo root (not in a subfolder)

**Custom domain not working:**
- DNS changes take 5–30 minutes to propagate
- Check your registrar's DNS settings match GitHub's IPs
- In GitHub Settings > Pages, verify the domain is listed and shows "DNS check successful"

**Need help?** GitHub Pages docs: https://docs.github.com/en/pages
