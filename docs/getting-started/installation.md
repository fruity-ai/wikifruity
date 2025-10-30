# Installation

This guide will walk you through setting up WikiFruity locally for development and contributing to the wiki. Follow these steps to get your development environment ready.

## Prerequisites

Before you begin, make sure you have the following installed on your system:

### Required Software

!!! warning "System Requirements"
    - **Python 3.7 or higher** - Required for MkDocs
    - **Git** - For version control and cloning the repository
    - **pip** - Python package manager (usually comes with Python)

### Verify Your Setup

Check that you have the required software installed:

```bash
# Check Python version
python --version
# or
python3 --version

# Check pip version
pip --version
# or
pip3 --version

# Check Git version
git --version
```

!!! tip "Python Version"
    If you have both Python 2 and Python 3 installed, you may need to use `python3` and `pip3` commands instead of `python` and `pip`.

## Step 1: Clone the Repository

First, clone the WikiFruity repository to your local machine:

```bash
# Clone the repository
git clone https://github.com/your-username/wikifruity.git

# Navigate to the project directory
cd wikifruity
```

## Step 2: Set Up Python Virtual Environment

It's recommended to use a virtual environment to isolate the project dependencies:

=== "Using venv (Recommended)"
    ```bash
    # Create a virtual environment
    python -m venv venv
    
    # Activate the virtual environment
    # On macOS/Linux:
    source venv/bin/activate
    
    # On Windows:
    venv\Scripts\activate
    ```

=== "Using conda"
    ```bash
    # Create a conda environment
    conda create -n wikifruity python=3.9
    
    # Activate the environment
    conda activate wikifruity
    ```

!!! info "Virtual Environment Benefits"
    Using a virtual environment ensures that project dependencies don't conflict with your system Python packages and makes the setup reproducible across different machines.

## Step 3: Install Dependencies

Install MkDocs and all required plugins:

```bash
# Install MkDocs and Material theme
pip install mkdocs mkdocs-material

# Install additional plugins
pip install mkdocs-minify-plugin
```

### Alternative: Install from Requirements File

If a `requirements.txt` file is available in the repository:

```bash
pip install -r requirements.txt
```

## Step 4: Verify Installation

Test that MkDocs is installed correctly:

```bash
# Check MkDocs version
mkdocs --version

# Validate the configuration
mkdocs build --strict
```

If everything is set up correctly, you should see output confirming the MkDocs version and a successful build.

## Step 5: Serve the Site Locally

Now you can serve the wiki locally for development:

```bash
# Start the development server
mkdocs serve
```

This will start a local development server, typically at `http://127.0.0.1:8000`. The server includes:

- **Live reload** - Changes to markdown files are reflected immediately
- **Search functionality** - Full search works locally
- **All theme features** - Dark/light mode, navigation, etc.

!!! success "Development Server Running"
    Once the server is running, you can open your browser and navigate to `http://127.0.0.1:8000` to view the wiki locally.

## Optional: Development Tools

For an enhanced development experience, consider installing these additional tools:

### Code Editor Extensions

If you're using **Visual Studio Code**, install these extensions:

- **Markdown All in One** - Enhanced markdown editing
- **markdownlint** - Markdown linting and style checking
- **Material Theme Icons** - Better file icons

### Pre-commit Hooks

Set up pre-commit hooks to maintain code quality:

```bash
# Install pre-commit
pip install pre-commit

# Install the git hooks
pre-commit install
```

## Troubleshooting

### Common Issues and Solutions

#### Python Version Issues
```bash
# If you get a Python version error
python3 -m pip install mkdocs mkdocs-material
```

#### Permission Denied Errors
```bash
# On macOS/Linux, try using --user flag
pip install --user mkdocs mkdocs-material
```

#### Port Already in Use
```bash
# Use a different port
mkdocs serve --dev-addr=127.0.0.1:8001
```

#### Build Failures
```bash
# Clean build (removes site directory)
mkdocs build --clean

# Verbose output for debugging
mkdocs build --verbose
```

### Getting Help

If you encounter issues not covered here:

1. Check the [MkDocs documentation](https://www.mkdocs.org/)
2. Review the [Material theme documentation](https://squidfunk.github.io/mkdocs-material/)
3. Look for similar issues in the project's GitHub Issues
4. Ask for help in the project's discussion forum or chat

## Next Steps

With your development environment set up, you're ready to:

1. **Explore the codebase** - Familiarize yourself with the project structure
2. **Try the Quick Start guide** - Get hands-on experience with basic workflows
3. **Read the Contributing guidelines** - Learn how to contribute effectively
4. **Start making changes** - Edit content and see your changes live

---

Congratulations! Your WikiFruity development environment is now ready. Head over to the [Quick Start](quick-start.md) guide to begin exploring the wiki's features.