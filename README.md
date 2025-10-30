# WikiFruity 🍊

A modern, responsive wiki powered by MkDocs and Material Design. Perfect for documentation, knowledge bases, project wikis, and collaborative content creation.

[![Deploy MkDocs to GitHub Pages](https://github.com/fruity-ai/wikifruity/actions/workflows/ci.yml/badge.svg)](https://github.com/your-username/wikifruity/actions/workflows/ci.yml)
[![MkDocs](https://img.shields.io/badge/MkDocs-1.5+-blue.svg)](https://www.mkdocs.org/)
[![Material Theme](https://img.shields.io/badge/Material-Theme-indigo.svg)](https://squidfunk.github.io/mkdocs-material/)

## ✨ Features

- **📱 Responsive Design** - Beautiful on desktop, tablet, and mobile
- **🌓 Dark/Light Mode** - Automatic theme switching with user preference
- **🔍 Full-Text Search** - Instantly find content across all pages
- **⚡ Live Reload** - See changes immediately during development
- **🎨 Material Design** - Modern, clean, and professional appearance
- **📝 Markdown-First** - Write content in familiar markdown syntax
- **🔗 Navigation** - Intuitive structure with breadcrumbs and TOC
- **🚀 Auto-Deploy** - Automatic deployment to GitHub Pages
- **🎯 SEO Optimized** - Built-in meta tags and structured data
- **🔧 Extensible** - Rich plugin ecosystem and customization options

## 🚀 Quick Start

### Prerequisites

- Python 3.7 or higher
- Git
- pip (Python package manager)

### Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/your-username/wikifruity.git
   cd wikifruity
   ```

2. **Set up virtual environment** (recommended)
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

4. **Serve locally**
   ```bash
   mkdocs serve
   ```

5. **Open in browser**
   Navigate to `http://127.0.0.1:8000`

## 📁 Project Structure

```
wikifruity/
├── docs/                      # Content directory
│   ├── index.md              # Homepage
│   ├── getting-started/      # Getting started guides
│   ├── user-guide/          # User documentation
│   ├── api/                 # API reference
│   └── contributing/        # Contributing guidelines
├── .github/workflows/        # GitHub Actions
├── mkdocs.yml               # MkDocs configuration
├── requirements.txt         # Python dependencies
└── README.md               # This file
```

## 🛠️ Development

### Local Development

1. **Start the development server**
   ```bash
   mkdocs serve
   ```
   The site will be available at `http://127.0.0.1:8000` with live reload enabled.

2. **Make changes**
   Edit markdown files in the `docs/` directory. Changes will be reflected immediately.

3. **Add new pages**
   - Create new `.md` files in the appropriate directory
   - Update the `nav` section in `mkdocs.yml`

### Building the Site

```bash
# Build the static site
mkdocs build

# Build with strict mode (recommended)
mkdocs build --strict

# Clean build
mkdocs build --clean
```

## 🚀 Deployment

### Automatic Deployment (GitHub Pages)

This wiki is configured for automatic deployment to GitHub Pages:

1. **Enable GitHub Pages**
   - Go to your repository settings
   - Navigate to "Pages" section
   - Set source to "GitHub Actions"

2. **Push to main branch**
   ```bash
   git add .
   git commit -m "Your commit message"
   git push origin main
   ```

3. **Automatic build and deploy**
   GitHub Actions will automatically build and deploy your site to:
   `https://fruity-ai.github.io/wikifruity`

### Manual Deployment

```bash
# Deploy directly to GitHub Pages
mkdocs gh-deploy

# Deploy to a specific branch
mkdocs gh-deploy --remote-branch gh-pages
```

## ⚙️ Configuration

### Site Settings

Edit `mkdocs.yml` to customize:

- **Site information** - Name, description, URL
- **Theme settings** - Colors, fonts, features
- **Navigation structure** - Page organization
- **Plugins** - Additional functionality
- **Extensions** - Markdown enhancements

### Theme Customization

The Material theme offers extensive customization options:

```yaml
theme:
  name: material
  palette:
    - scheme: default
      primary: indigo
      accent: indigo
  features:
    - navigation.tabs
    - navigation.sections
    - search.highlight
```

## 📝 Content Creation

### Writing Content

1. **Create markdown files** in the `docs/` directory
2. **Use standard markdown syntax** with enhanced features
3. **Add to navigation** in `mkdocs.yml`

### Markdown Features

- **Admonitions** - Call-out boxes for notes, tips, warnings
- **Code highlighting** - Syntax highlighting for 100+ languages
- **Tabs** - Organize content with tabbed sections
- **Tables** - Rich table formatting
- **Math** - LaTeX mathematical expressions
- **Diagrams** - Mermaid flowcharts and diagrams

Example:
```markdown
!!! tip "Pro Tip"
    This creates a helpful tip box that stands out to readers.

```python
def hello_world():
    print("Hello from WikiFruity!")
```

## 🤝 Contributing

We welcome contributions! Please see our [Contributing Guidelines](docs/contributing/guidelines.md) for details.

### Quick Contribution Steps

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Make your changes
4. Test locally (`mkdocs serve`)
5. Commit your changes (`git commit -m 'Add amazing feature'`)
6. Push to the branch (`git push origin feature/amazing-feature`)
7. Open a Pull Request

## 📚 Documentation

- **[Getting Started](docs/getting-started/introduction.md)** - Introduction and setup
- **[User Guide](docs/user-guide/overview.md)** - Comprehensive usage documentation
- **[API Reference](docs/api/overview.md)** - Technical reference
- **[Contributing](docs/contributing/guidelines.md)** - How to contribute

## 🔧 Troubleshooting

### Common Issues

**Build fails with import errors:**
```bash
pip install -r requirements.txt
```

**Port already in use:**
```bash
mkdocs serve --dev-addr 127.0.0.1:8001
```

**Changes not reflecting:**
- Check that `mkdocs serve` is running
- Ensure files are saved
- Try hard refresh (Ctrl+F5)

### Getting Help

- Check the [MkDocs documentation](https://www.mkdocs.org/)
- Review [Material theme docs](https://squidfunk.github.io/mkdocs-material/)
- Search existing [GitHub Issues](https://github.com/your-username/wikifruity/issues)
- Create a new issue if needed

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- [MkDocs](https://www.mkdocs.org/) - The static site generator
- [Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) - The beautiful theme
- [Python-Markdown](https://python-markdown.github.io/) - Markdown processing
- [GitHub Pages](https://pages.github.com/) - Free hosting

---

**Happy documenting! 🎉**

For questions or support, please [open an issue](https://github.com/your-username/wikifruity/issues) or check our [documentation](docs/getting-started/introduction.md).
