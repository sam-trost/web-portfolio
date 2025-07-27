# Samuel Trost - Web Portfolio

A professional portfolio website showcasing Samuel Trost's software engineering experience and expertise.

## Overview

This is a responsive, single-page portfolio website featuring a clean, modern design with tabbed navigation. The site highlights professional experience in software engineering, AI/ML, cloud architecture, and DevOps.

## Features

- **Responsive Design**: Optimized for desktop and mobile devices
- **Tabbed Navigation**: Easy-to-navigate sections including About, Experience, Skills, and Contact
- **Professional Showcase**: Detailed work experience at nlx.ai and Trane Technologies
- **Skills Display**: Visual representation of technical competencies
- **Contact Form**: Integrated contact form for professional inquiries
- **Modern UI**: Clean, Google Material Design-inspired styling

## Live Demo

This portfolio is hosted on GitHub Pages and can be viewed at:
**[https://sam-trost.github.io/web-portfolio/](https://sam-trost.github.io/web-portfolio/)**

## Quick Start

### Viewing the Portfolio

**Option 1: View Online**

- Visit the live site at [https://sam-trost.github.io/web-portfolio/](https://sam-trost.github.io/web-portfolio/)

**Option 2: Local Development**

1. Clone or download this repository
2. Open `docs/index.html` in your web browser
3. Navigate through the different sections using the tab navigation

### Local Development

No build process required - this is a static HTML website.

```bash
# Simply open the file in your browser
open docs/index.html

# Or serve locally with Python (optional)
cd docs
python -m http.server 8000
# Then visit http://localhost:8000
```

## Deployment

This site is automatically deployed to GitHub Pages from the `docs/` folder on the main branch.

### GitHub Pages Setup

1. **Repository Settings**: Go to your repository settings on GitHub
2. **Pages Section**: Navigate to the "Pages" section in the left sidebar
3. **Source Configuration**:
   - Source: Deploy from a branch
   - Branch: `main` (or your default branch)
   - Folder: `/docs`
4. **Save**: Click "Save" to enable GitHub Pages
5. **Access**: Your site will be available at `https://[username].github.io/[repository-name]/`

### Updating the Live Site

Any changes pushed to the `docs/` folder on the main branch will automatically update the live site within a few minutes.

### Custom Domain with AWS Route53

To use a custom domain (e.g., `samuelstrost.com`) with your GitHub Pages site:

#### Prerequisites

- A registered domain name
- AWS account with Route53 access
- GitHub repository with Pages enabled

#### Step 1: Configure GitHub Pages Custom Domain

1. **Add CNAME file**: Create a file named `CNAME` in your `docs/` folder
   ```
   echo "yourdomain.com" > docs/CNAME
   ```
2. **GitHub Settings**:
   - Go to repository Settings → Pages
   - Under "Custom domain", enter your domain name
   - Enable "Enforce HTTPS" (recommended)
3. **Commit and push** the CNAME file to your repository

#### Step 2: Configure AWS Route53

1. **Create Hosted Zone** (if not already created):

   - Go to AWS Route53 console
   - Click "Create hosted zone"
   - Enter your domain name (e.g., `yourdomain.com`)
   - Note the Name Servers (NS) provided

2. **Update Domain Registrar**:

   - Go to your domain registrar (GoDaddy, Namecheap, etc.)
   - Update the nameservers to use the Route53 NS records

3. **Create DNS Records**:

   **For Apex Domain (yourdomain.com):**

   ```
   Type: A
   Name: @ (or leave blank)
   Value: 185.199.108.153
   TTL: 300

   Type: A
   Name: @ (or leave blank)
   Value: 185.199.109.153
   TTL: 300

   Type: A
   Name: @ (or leave blank)
   Value: 185.199.110.153
   TTL: 300

   Type: A
   Name: @ (or leave blank)
   Value: 185.199.111.153
   TTL: 300
   ```

   **For WWW Subdomain (www.yourdomain.com):**

   ```
   Type: CNAME
   Name: www
   Value: [username].github.io
   TTL: 300
   ```

#### Step 3: Verification

1. **DNS Propagation**: Wait 5-60 minutes for DNS changes to propagate
2. **Test Domain**: Visit your custom domain to verify it works
3. **SSL Certificate**: GitHub automatically provisions SSL certificates for custom domains

#### Troubleshooting

- **DNS Propagation**: Use tools like `dig` or online DNS checkers to verify records
- **HTTPS Issues**: Ensure "Enforce HTTPS" is enabled in GitHub Pages settings
- **404 Errors**: Verify the CNAME file contains only your domain name (no protocol)

#### Example Commands for Verification

```bash
# Check DNS resolution
dig yourdomain.com
dig www.yourdomain.com

# Check if GitHub Pages recognizes the domain
curl -I https://yourdomain.com
```

## Project Structure

```
web-portfolio/
├── docs/
│   └── index.html          # Main portfolio page
└── README.md              # This file
```

## Sections

### About Me

Professional summary highlighting software engineering leadership and innovation focus.

### Experience

- **nlx.ai** (2022 - Present): AI-powered NLP tools and enterprise Generative AI solutions
- **Trane Technologies** (2008 - Present): Cloud architecture and digital transformation leadership

### Skills

Technical competencies including:

- Cloud Architecture & AWS
- AI & Machine Learning
- DevOps & Automation
- Team Leadership
- Digital Transformation

### Contact

Professional contact form and social media links.

## Technologies Used

- **HTML5**: Semantic markup and structure
- **CSS3**: Modern styling with flexbox and responsive design
- **JavaScript**: Interactive tabbed navigation and form handling
- **Google Fonts**: Roboto font family for clean typography

## Contact Information

- **LinkedIn**: [sam-trost](https://www.linkedin.com/in/sam-trost/)
- **GitHub**: [sam-trost](https://github.com/sam-trost)
- **Location**: Walnut Cove, NC

## License

© 2024 Samuel Trost. All rights reserved.
