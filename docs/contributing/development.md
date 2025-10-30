# Development Guide

Learn how to set up a development environment and contribute code to WikiFruity.

## Development Setup

### Prerequisites

Before you begin, ensure you have the following installed:

- Python 3.8 or higher
- Git
- A text editor or IDE

### Local Development Environment

1. Fork the repository on GitHub
2. Clone your fork locally:
   ```bash
   git clone https://github.com/YOUR-USERNAME/wikifruity.git
   cd wikifruity
   ```

3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

4. Start the development server:
   ```bash
   mkdocs serve
   ```

5. Open your browser to `http://127.0.0.1:8000`

## Project Structure

```
wikifruity/
├── docs/               # Documentation source files
├── mkdocs.yml         # MkDocs configuration
├── requirements.txt   # Python dependencies
└── .github/           # GitHub workflows
```

## Development Workflow

1. Create a new branch for your feature:
   ```bash
   git checkout -b feature/your-feature-name
   ```

2. Make your changes and test locally

3. Commit your changes:
   ```bash
   git add .
   git commit -m "Description of changes"
   ```

4. Push to your fork:
   ```bash
   git push origin feature/your-feature-name
   ```

5. Open a Pull Request

## Code Standards

### Markdown Style

- Use ATX-style headers (`#` prefix)
- Keep lines under 120 characters when possible
- Use fenced code blocks with language identifiers

### Python Code

- Follow PEP 8 style guide
- Use type hints where appropriate
- Write docstrings for functions and classes

## Testing

Run the build in strict mode to catch warnings:

```bash
mkdocs build --clean --strict --verbose
```

## Documentation

When adding new features:

1. Update relevant documentation files
2. Add examples and code snippets
3. Update the navigation in `mkdocs.yml` if needed

## Getting Help

If you need help with development:

- Check the [Contributing Guidelines](guidelines.md)
- Open an issue on GitHub
- Join our community discussions

## Related Documentation

- [Contributing Guidelines](guidelines.md) - General contribution guidelines
