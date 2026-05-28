# Solargation® Website

Static HTML website prepared for deployment through a Git repository in cPanel.

## Pages

- `index.html`
- `contact.html`
- `energy.html`
- `landuse.html`
- `crops.html`
- `wateruse.html`
- `news.html`

## Required cPanel deployment file

This repository includes a valid `.cpanel.yml` file at the repository root. cPanel Git Version Control requires this file in the top-level directory of the repository before the **Deploy HEAD Commit** workflow will run.

The included deployment file copies the website into:

```bash
$HOME/public_html/
```

That is the standard primary-domain web root for many cPanel accounts.

## Important deployment note

If this repository is being deployed to an addon domain or subdomain, update the first deployment task in `.cpanel.yml` before committing:

```yaml
- export DEPLOYPATH=$HOME/public_html/
```

Examples:

```yaml
- export DEPLOYPATH=$HOME/example.com/
```

or

```yaml
- export DEPLOYPATH=$HOME/public_html/example-subdomain/
```

Use the exact document root shown in cPanel for that domain.

## cPanel Git deployment steps

1. Upload or push this folder as the root of your GitHub repository.
2. Confirm `.cpanel.yml` is committed at the repository root.
3. In cPanel, open **Git Version Control**.
4. Clone or connect the GitHub repository.
5. Pull the latest branch if needed.
6. Click **Deploy HEAD Commit**.
7. Confirm the files appear in the target `DEPLOYPATH` directory.

## Contact form limitation

This is a static website. The contact form opens the visitor's email client with a prepared message to `info@phoebusfund.com`. To send email silently from the website, connect the form to a backend or a third-party form service.
