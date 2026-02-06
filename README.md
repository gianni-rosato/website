# Starter Website Project

Welcome to your first website project! This repository contains a basic template
for a website built using HTML and CSS. It's designed to be simple, clean, and
well-documented to help you understand how web pages are structured and styled.

## Fish Shell

First, ensure Fish is installed. If you use Homebrew:

```bash
brew install fish
```

Then you need to add Fish to the list of approved shells and change your
default. The path differs depending on your Mac:

**For Apple Silicon (M1/M2/M3):**

```bash
sudo sh -c 'echo /opt/homebrew/bin/fish >> /etc/shells'
chsh -s /opt/homebrew/bin/fish
```

You'll be prompted for your password. After running these commands, open a new
terminal window or tab, and you should be in Fish.

To verify the change took effect:

```bash
echo $SHELL
```

**Alternative approach:** If you'd rather not change your system login shell,
you can set Fish as the default only for your terminal app. In Terminal.app, go
to Settings > General > "Shells open with" and select Command, entering the path
to Fish. iTerm2 users can set this under Settings > Profiles > General >
Command.

One note: since macOS now uses zsh as its default, some system scripts or
instructions you encounter online may assume zsh syntax. If you ever need to run
something that requires bash or zsh, you can always type `bash` or `zsh` to
start that shell temporarily.

## GitHub SSH Key

Cloning your repos with SSH is the best way to be able to interact with your
repository without much fuss.

First, generate a new SSH key if you don't have one already. Open your terminal
and run:

```
ssh-keygen -t ed25519 -C "your_email@example.com"
```

When prompted, press Enter to accept the default file location. You can add a
passphrase for extra security or press Enter again to skip it.

Next, copy your public key to the clipboard. The command depends on your system:

On macOS: `pbcopy < ~/.ssh/id_ed25519.pub` On Windows (Git Bash):
`cat ~/.ssh/id_ed25519.pub | clip` On Linux: `cat ~/.ssh/id_ed25519.pub` and
manually copy the output

Now add it to GitHub. Go to github.com, click your profile photo in the
top-right, choose Settings, then select SSH and GPG keys from the sidebar. Click
New SSH key, give it a descriptive title (like "MacBook Pro" or "Work Desktop"),
paste the key into the Key field, and click Add SSH key.

Finally, test the connection:

```
ssh -T git@github.com
```

You should see a message saying you've successfully authenticated. If you used a
passphrase, you'll need to enter it.

If you generated a key with a different algorithm like RSA, just replace
`id_ed25519` with `id_rsa` in the commands above.

## Live Server

First ensure you have Node.js installed:

```bash
node --version
```

If not installed, get it via Homebrew:

```bash
brew install node
```

Then install live-server globally:

```bash
npm install -g live-server
```

If you get permission errors, avoid using sudo and instead fix npm's
permissions:

```bash
mkdir ~/.npm-global
npm config set prefix '~/.npm-global'
echo 'export PATH=~/.npm-global/bin:$PATH' >> ~/.zshrc
source ~/.zshrc
npm install -g live-server
```

To use it, navigate to your project folder and run:

```bash
live-server
```

This opens your default browser at `http://127.0.0.1:8080` with live reload
enabled.

If you prefer not to install globally, you can use npx without installing:

```bash
npx live-server
```

Or add it as a dev dependency in a specific project:

```bash
npm install --save-dev live-server
```

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
