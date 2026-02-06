# Starter Website Project

Welcome to your first website project! This repository contains a basic template
for a website built using HTML and CSS. It's designed to be simple, clean, and
well-documented to help you understand how web pages are structured and styled.

## Project Structure

- `index.html`: The main structure and content of your website.
- `style.css`: The styling rules that define how your website looks.
- `CNAME`: A configuration file for setting up a custom domain on GitHub Pages.

## How Basic Website Setup Works

A website is essentially a collection of files stored on a computer (server)
that is connected to the internet. When you visit a URL (like
`www.example.com`), your browser requests these files and renders them for you
to see.

1. **HTML (HyperText Markup Language):** This is the "bones" of your website. It
   uses tags (like `<h1>`, `<p>`, `<div>`) to define the structure and content.
2. **CSS (Cascading Style Sheets):** This is the "skin" or "paint" of your
   website. It defines the colors, fonts, spacing, and layout of the HTML
   elements.
3. **Hosting:** To make your website accessible to everyone, you need to host
   it. GitHub Pages is a free service that hosts your website directly from your
   GitHub repository.

## Setting Up GitHub Pages

1. **Push your code to GitHub:** Ensure all your files (`index.html`,
   `style.css`, etc.) are committed and pushed to a repository on GitHub.
2. **Enable GitHub Pages:**
   - Go to your repository on GitHub.
   - Click on **Settings**.
   - In the left-hand sidebar, click on **Pages**.
   - Under **Build and deployment**, select **Deploy from a branch**.
   - Choose your `main` branch and the `/ (root)` folder, then click **Save**.
3. **Wait for Deployment:** GitHub will take a minute or two to build and deploy
   your site. You'll see a message like "Your site is live at..." with a URL.

## Using a Custom Domain with CNAME

If you have purchased a domain name (e.g., from Namecheap or Google Domains) and
want to use it instead of the `github.io` address:

1. **Add a CNAME file:**
   - Create a file named `CNAME` (no file extension) in the root of your
     repository.
   - Inside the file, type your domain name (e.g., `www.yourdomain.com`).
   - Save and push this change to GitHub.
2. **Update GitHub Settings:**
   - Go back to **Settings > Pages** in your GitHub repository.
   - Under **Custom domain**, type your domain name and click **Save**.
   - GitHub will automatically check if the CNAME file exists and match it.
3. **Configure DNS with your Domain Provider:**
   - Log in to your domain provider's dashboard.
   - Create a **CNAME record** pointing your subdomain (like `www`) to
     `yourusername.github.io`.
   - Alternatively, create **A records** pointing your root domain to GitHub's
     IP addresses (check GitHub's official documentation for the latest IP
     addresses).
4. **Enforce HTTPS:** Once your domain is verified and the DNS has propagated
   (which can take up to 24-48 hours), check the **Enforce HTTPS** box in the
   GitHub Pages settings to ensure a secure connection.

Happy coding!
