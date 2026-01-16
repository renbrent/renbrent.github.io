# Brent Basiano - Portfolio Site

Professional portfolio site built with Hugo and deployed on GitHub Pages.

## 🚀 Live Site

Visit: [https://renbrent.github.io](https://renbrent.github.io)

## 📋 Features

- **Responsive Design**: Mobile-first approach, optimized for all devices
- **Performance Optimized**: Lighthouse scores ≥90 across all categories
- **Accessibility**: WCAG 2.1 AA compliant
- **Projects Showcase**: Detailed project cards with demos and GitHub links
- **Professional Resume**: Downloadable PDF and online version
- **Contact Section**: Easy ways for recruiters to reach out

## 🛠️ Built With

- [Hugo](https://gohugo.io/) - Static site generator
- [hugo-profile](https://github.com/gurusabarish/hugo-profile) - Portfolio theme
- GitHub Pages - Hosting
- GitHub Actions - CI/CD deployment

## 🏗️ Project Structure

```
renbrent.github.io/
├── .github/
│   ├── workflows/
│   │   └── deploy.yml       # GitHub Actions deployment
│   ├── agents/              # SpecKit agent definitions
│   └── prompts/             # SpecKit prompt files
├── .specify/                # SpecKit framework
│   ├── memory/
│   │   └── constitution.md  # Project governance
│   ├── scripts/             # Automation scripts
│   └── templates/           # Document templates
├── archetypes/              # Hugo content templates
├── content/                 # Markdown content
├── layouts/                 # Custom Hugo templates
├── static/                  # Static assets (images, PDFs)
│   ├── images/
│   └── files/
├── themes/                  # Hugo themes (git submodules)
├── hugo.toml               # Hugo configuration
└── README.md
```

## 🚦 Local Development

### Prerequisites

- [Hugo Extended](https://gohugo.io/installation/) v0.121.0 or later
- Git

### Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/renbrent/renbrent.github.io.git
   cd renbrent.github.io
   ```

2. Initialize the theme submodule:
   ```bash
   git submodule update --init --recursive
   ```

3. Run the development server:
   ```bash
   hugo server -D
   ```

4. Open [http://localhost:1313](http://localhost:1313) in your browser

### Making Changes

1. Edit content in `hugo.toml` for site-wide settings
2. Add/update projects, experience, or education directly in the configuration
3. Place static files (images, resume PDF) in the `static/` directory
4. Test locally before committing

## 📝 Customization Guide

### Update Personal Information

Edit [hugo.toml](hugo.toml):
- Change `title` to your name
- Update `params.hero.title`, `params.hero.subtitle`, and `params.hero.content`
- Modify `params.contact.email` with your email

### Add Projects

In [hugo.toml](hugo.toml), add project entries under `params.projects.items`:
```toml
[[params.projects.items]]
  title = "Your Project Name"
  content = "Description of your project"
  image = "/images/projects/yourproject.jpg"
  badges = ["Technology1", "Technology2"]
  
  [[params.projects.items.links]]
    icon = "fab fa-github"
    url = "https://github.com/yourusername/project"
```

### Update Experience

Modify `params.experience.items` in [hugo.toml](hugo.toml) with your work history.

### Add Your Resume

1. Place your PDF resume in `static/files/resume.pdf`
2. The download button in the hero section will automatically link to it

### Add Your Photo

1. Add your profile photo to `static/images/profile.jpg`
2. Update the `image` paths in the configuration if using a different filename

## 🚀 Deployment

The site automatically deploys to GitHub Pages when you push to the `main` branch.

### GitHub Pages Setup

1. Go to repository **Settings** > **Pages**
2. Set **Source** to "GitHub Actions"
3. Push changes to `main` branch
4. GitHub Actions will build and deploy automatically

### Custom Domain (Optional)

To use a custom domain:
1. Create `static/CNAME` file with your domain
2. Update `baseURL` in [hugo.toml](hugo.toml)
3. Configure DNS with your domain provider

## 📊 Performance Standards

This site follows strict performance requirements (see [.specify/memory/constitution.md](.specify/memory/constitution.md)):

- **Core Web Vitals**: LCP <2.5s, FID <100ms, CLS <0.1
- **Lighthouse Scores**: Performance ≥90, Accessibility ≥95, Best Practices ≥95, SEO ≥95
- **Bundle Sizes**: JS <100KB, CSS <50KB (gzipped)

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

## 🤝 Contributing

This is a personal portfolio site. However, if you find bugs or have suggestions:
1. Open an issue describing the problem
2. Fork the repository
3. Create a feature branch
4. Submit a pull request

## 📞 Contact

- **Email**: your.email@example.com
- **GitHub**: [@renbrent](https://github.com/renbrent)
- **LinkedIn**: [Your Profile](https://linkedin.com/in/yourprofile)

---

**Built with** ❤️ **using Hugo**
