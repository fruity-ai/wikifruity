# API Reference Overview

Welcome to the WikiFruity API Reference! This section provides comprehensive technical documentation for developers who want to extend, customize, or integrate with WikiFruity.

## 🎯 What's Covered

This API reference covers several key areas:

- **MkDocs Configuration API** - Programmatic configuration and customization
- **Plugin Development** - Creating custom plugins and extensions
- **Theme Customization** - Extending the Material theme
- **Content Processing** - Working with markdown and content transformation
- **Deployment APIs** - Automation and CI/CD integration

## 📚 API Categories

### Configuration API

The MkDocs configuration system provides a powerful way to customize your wiki programmatically.

#### Key Components
- **Site Configuration** - Basic site metadata and settings
- **Theme Configuration** - Appearance and behavior customization  
- **Plugin Configuration** - Enable and configure functionality
- **Navigation Configuration** - Structure and organization

#### Example Configuration
```python
# mkdocs.yml as Python dict
config = {
    'site_name': 'WikiFruity',
    'theme': {
        'name': 'material',
        'palette': {
            'scheme': 'default',
            'primary': 'indigo'
        }
    },
    'plugins': ['search', 'minify']
}
```

### Plugin Development API

Create custom plugins to extend WikiFruity functionality.

#### Plugin Structure
```python
from mkdocs.plugins import BasePlugin
from mkdocs.config import config_options

class MyPlugin(BasePlugin):
    config_scheme = (
        ('option_name', config_options.Type(str, default='default')),
    )
    
    def on_page_markdown(self, markdown, page, config, files):
        # Process markdown before conversion
        return markdown
    
    def on_page_content(self, html, page, config, files):
        # Process HTML after conversion
        return html
```

#### Available Hooks
- `on_startup` - Called when MkDocs starts
- `on_config` - Process configuration
- `on_files` - Access to all site files
- `on_page_markdown` - Process raw markdown
- `on_page_content` - Process generated HTML
- `on_page_context` - Modify template context
- `on_post_build` - Post-processing after build

### Theme Customization API

Extend and customize the Material theme for unique branding and functionality.

#### Template Overrides
```html
<!-- custom_theme/main.html -->
{% extends "base.html" %}

{% block content %}
  <div class="custom-wrapper">
    {{ super() }}
  </div>
{% endblock %}
```

#### Custom CSS/JavaScript
```css
/* docs/stylesheets/extra.css */
:root {
  --md-primary-fg-color: #your-color;
  --md-accent-fg-color: #your-accent;
}

.custom-element {
  /* Your custom styles */
}
```

### Content Processing API

Work with markdown content and implement custom processors.

#### Markdown Extensions
```python
from markdown.extensions import Extension
from markdown.preprocessors import Preprocessor

class CustomPreprocessor(Preprocessor):
    def run(self, lines):
        # Process lines before markdown parsing
        return lines

class CustomExtension(Extension):
    def extendMarkdown(self, md):
        md.preprocessors.register(
            CustomPreprocessor(md), 'custom', 175
        )
```

#### File Processing
```python
def process_files(files):
    for file in files:
        if file.src_path.endswith('.md'):
            # Process markdown files
            content = file.content_string
            # Modify content
            file.content_string = processed_content
    return files
```

## 🔧 Integration Points

### Build System Integration

#### GitHub Actions API
```yaml
# .github/workflows/custom.yml
- name: Custom Processing
  run: |
    python scripts/custom_processor.py
    mkdocs build --config-file custom-mkdocs.yml
```

#### Webhook Integration
```python
# webhook_handler.py
import mkdocs
from mkdocs.config import load_config

def handle_webhook(payload):
    config = load_config('mkdocs.yml')
    # Process webhook data
    # Trigger rebuild if needed
    mkdocs.build(config)
```

### External Service Integration

#### Search API Integration
```javascript
// Custom search integration
async function customSearch(query) {
    const response = await fetch(`/api/search?q=${query}`);
    const results = await response.json();
    return processResults(results);
}
```

#### Analytics Integration
```javascript
// Custom analytics
function trackPageView(page) {
    // Send to your analytics service
    analytics.track('page_view', {
        page: page.title,
        url: page.url,
        timestamp: new Date()
    });
}
```

## 📝 Common Use Cases

### Custom Content Types

Create specialized content processors for different types of documentation:

```python
class APIDocProcessor(BasePlugin):
    def on_page_markdown(self, markdown, page, config, files):
        if page.meta.get('type') == 'api':
            # Process API documentation specifically
            return self.process_api_doc(markdown)
        return markdown
```

### Dynamic Navigation

Generate navigation structure programmatically:

```python
def generate_nav_from_files(files):
    nav = []
    for file in files:
        if file.src_path.startswith('auto-generated/'):
            nav.append({
                file.page.title: file.dest_path
            })
    return nav
```

### Content Validation

Implement content quality checks:

```python
class ContentValidator(BasePlugin):
    def on_page_content(self, html, page, config, files):
        # Validate content structure
        self.check_headings(html)
        self.check_links(html, files)
        self.check_images(html)
        return html
```

## 🚀 Advanced Patterns

### Multi-language Support

```python
class I18nPlugin(BasePlugin):
    def on_config(self, config):
        # Setup language-specific configurations
        lang = config.get('theme', {}).get('language', 'en')
        self.setup_language(lang, config)
        return config
```

### Performance Optimization

```python
class CachePlugin(BasePlugin):
    def __init__(self):
        self.cache = {}
    
    def on_page_markdown(self, markdown, page, config, files):
        cache_key = hash(markdown)
        if cache_key in self.cache:
            return self.cache[cache_key]
        
        processed = self.expensive_processing(markdown)
        self.cache[cache_key] = processed
        return processed
```

### Custom Deployment

```python
class CustomDeploy(BasePlugin):
    def on_post_build(self, config):
        # Custom deployment logic
        self.deploy_to_cdn(config['site_dir'])
        self.update_search_index()
        self.notify_services()
```

## 📊 Configuration Reference

### Complete Configuration Schema

```yaml
# Full configuration example
site_name: WikiFruity
site_description: Comprehensive wiki documentation
site_author: Your Name
site_url: https://example.com

# Repository information
repo_name: username/repo
repo_url: https://github.com/username/repo

# Build directory
site_dir: site

# Source directory
docs_dir: docs

# Theme configuration
theme:
  name: material
  custom_dir: custom_theme
  language: en
  features:
    - navigation.tabs
    - navigation.sections
    - navigation.expand
    - search.highlight
  palette:
    - scheme: default
      primary: indigo
      accent: indigo

# Plugins
plugins:
  - search:
      lang: en
      separator: '[\s\-,:!=\[\]()"`/]+|\.(?!\d)|&[lg]t;|(?!\b)(?=[A-Z][a-z])'
  - minify:
      minify_html: true
      minify_js: true
      minify_css: true

# Markdown extensions
markdown_extensions:
  - toc:
      permalink: true
  - pymdownx.highlight:
      anchor_linenums: true
  - pymdownx.inlinehilite
  - pymdownx.superfences
  - admonition
  - pymdownx.details

# Navigation structure
nav:
  - Home: index.md
  - API:
    - Overview: api/overview.md
    - Endpoints: api/endpoints.md

# Custom variables
extra:
  version: 1.0.0
  social:
    - icon: fontawesome/brands/github
      link: https://github.com/username/repo
```

## 🔍 Debugging and Development

### Debug Mode

Enable verbose output for development:

```bash
# Verbose build
mkdocs build --verbose

# Debug server
mkdocs serve --verbose --dev-addr=127.0.0.1:8000
```

### Plugin Development Tools

```python
import logging
logger = logging.getLogger('mkdocs.plugins.myplugin')

class DebugPlugin(BasePlugin):
    def on_config(self, config):
        logger.info(f"Config loaded: {config['site_name']}")
        return config
```

## 📚 Additional Resources

### Official Documentation
- [MkDocs Plugin API](https://www.mkdocs.org/user-guide/plugins/)
- [Material Theme Customization](https://squidfunk.github.io/mkdocs-material/customization/)
- [Python-Markdown Extensions](https://python-markdown.github.io/extensions/)

### Community Resources
- [MkDocs Plugin Collection](https://github.com/mkdocs/mkdocs/wiki/MkDocs-Plugins)
- [Material Theme Extensions](https://squidfunk.github.io/mkdocs-material/reference/)

### Example Implementations
- [Search Plugin Source](https://github.com/mkdocs/mkdocs/tree/master/mkdocs/contrib/search)
- [Material Theme Source](https://github.com/squidfunk/mkdocs-material)

---

This API reference provides the foundation for extending WikiFruity. For specific implementation details, see the [Endpoints](endpoints.md) documentation.