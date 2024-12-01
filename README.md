# Francisco Rebolledo's Personal Website

This repository contains the source code for my personal website, built with Hugo using the Toha theme.

## Theme

This site uses the [Toha theme](https://github.com/hugo-toha/toha) (v4), a clean and modern Hugo theme for personal portfolios. The theme is imported as a Hugo module in the `hugo.yaml` configuration file.

## Directory Structure

```
franresume/
├── .github/
│   └── workflows/        # GitHub Actions workflow configurations
├── assets/
│   └── images/          # Site images including background and logos
├── content/
│   └── sections/        # Content sections for the single-page layout
├── data/               
│   ├── en/             # English content data
│   └── site.yaml       # Site configuration data
├── layouts/
│   └── partials/       # Custom layout partials
├── public/             # Generated site (ignored in git)
├── static/             # Static files
├── hugo.yaml           # Hugo configuration file
└── go.mod             # Hugo modules configuration
```

## Running Locally

To run this site locally:

1. Prerequisites:
   - Install [Hugo Extended](https://gohugo.io/installation/) (v0.111.3 or later)
   - Install Go (v1.16 or later)
   - Install Node.js 18 or later and npm

2. Clone the repository:
   ```bash
   git clone https://github.com/franrebo84/franresume.git
   cd franresume
   ```

3. Install dependencies:
   ```bash
   npm install
   ```

4. Initialize and update Hugo modules:
   ```bash
   hugo mod init github.com/franrebo84/franresume
   hugo mod get -u
   ```

5. Start the Hugo server:
   ```bash
   hugo server -w
   ```

6. View the site at `http://localhost:1313`

## GitHub Actions Deployment

This site is automatically deployed using GitHub Actions. The workflow is configured in `.github/workflows/hugo.yaml` and is triggered by:
- Pushes to the main branch
- Manual triggers from the Actions tab

The workflow performs the following steps:

1. Sets up Ubuntu latest environment
2. Checks out the repository
3. Sets up Node.js 18
4. Installs node modules
5. Sets up Hugo (latest version with extended features)
6. Builds the site with minification
7. Uploads the artifact
8. Deploys to GitHub Pages

Key workflow features:
- Uses concurrent deployment control to prevent conflicts
- Maintains proper permissions using GitHub token
- Uses the latest versions of actions including:
  - actions/checkout@v4.1.1
  - actions/setup-node@v4
  - peaceiris/actions-hugo@v3.0.0
  - actions/upload-pages-artifact@v1
  - actions/deploy-pages@v2

## Deployment

The site is deployed in two locations:

1. GitHub Pages: https://franrebo84.github.io/
2. Custom Domain: https://me.rebo.ar

The custom domain is configured in the GitHub Pages settings and uses Cloudflare for DNS management.

## Analytics

Google Analytics 4 is implemented to track site usage. The configuration can be found in the `hugo.yaml` file under the `features.analytics` section.

## Contributing

If you find any issues or have suggestions for improvements, please feel free to open an issue or submit a pull request.

## License

This project is licensed under the MIT License - see the LICENSE file for details.
