# Quick Start

Welcome to the WikiFruity Quick Start guide! This page will get you up and running with the basics in just a few minutes. By the end of this guide, you'll know how to edit content, add new pages, and contribute to the wiki.

## 🎯 What You'll Learn

In this quick start, you'll learn how to:

- Edit existing wiki pages
- Add new pages and organize content
- Use basic markdown features and wiki syntax
- Preview your changes locally
- Build and deploy the wiki

!!! info "Before You Begin"
    Make sure you've completed the [Installation](installation.md) guide and have the wiki running locally with `mkdocs serve`.

## Step 1: Your First Edit

Let's start by making a simple edit to see the live reload in action:

1. **Open a markdown file** - Navigate to `docs/index.md` in your editor
2. **Make a change** - Add your name or a custom message to the welcome section
3. **Save the file** - The browser should automatically refresh and show your changes

!!! tip "Live Reload"
    With `mkdocs serve` running, any changes you make to markdown files will be reflected immediately in your browser. No need to manually refresh!

### Example Edit

Try changing this line in `docs/index.md`:

```markdown
# Welcome to WikiFruity
```

To something like:

```markdown
# Welcome to WikiFruity - [Your Name]'s Version
```

## Step 2: Create Your First Page

Now let's add a brand new page to the wiki:

1. **Create the file** - Create a new file called `docs/my-first-page.md`
2. **Add content** - Copy and paste the template below
3. **Update navigation** - Add the page to `mkdocs.yml`

### Page Template

```markdown
# My First Page

This is my first custom page in WikiFruity!

## Introduction

Here I can write about anything I want. Let me try some markdown features:

- **Bold text** for emphasis
- *Italic text* for style
- `Code snippets` for technical content

### Code Example

```python
def hello_world():
    print("Hello from WikiFruity!")
    return "Success"
```

## What's Next?

I can add more sections, images, and advanced features as I learn more about MkDocs and the Material theme.
```

### Add to Navigation

Open `mkdocs.yml` and add your new page to the `nav` section:

```yaml
nav:
  - Home: index.md
  - My First Page: my-first-page.md  # Add this line
  - Getting Started:
    - Introduction: getting-started/introduction.md
    # ... rest of the navigation
```

## Step 3: Explore Markdown Features

Let's try some of the advanced features available in this wiki:

### Admonitions (Callout Boxes)

Add these to your page to create eye-catching callouts:

```markdown
!!! note "This is a note"
    This creates a blue note box.

!!! tip "Pro Tip"
    This creates a green tip box.

!!! warning "Be Careful"
    This creates an orange warning box.

!!! danger "Important"
    This creates a red danger box.
```

### Tabs

Create organized content with tabs:

```markdown
=== "Tab 1"
    Content for the first tab.

=== "Tab 2"
    Content for the second tab.

=== "Tab 3"
    Content for the third tab.
```

### Code Blocks with Syntax Highlighting

```markdown
```python
# Python code example
def calculate_fibonacci(n):
    if n <= 1:
        return n
    return calculate_fibonacci(n-1) + calculate_fibonacci(n-2)
```

```javascript
// JavaScript code example
function greetUser(name) {
    console.log(`Hello, ${name}!`);
}
```
```

### Task Lists

```markdown
- [x] Complete the quick start guide
- [x] Learn basic markdown
- [ ] Add more advanced features
- [ ] Contribute to the wiki
```

## Step 4: Organize Your Content

### Creating Sections

To keep content organized, create subdirectories:

```bash
mkdir docs/tutorials
mkdir docs/examples
mkdir docs/reference
```

### Directory Structure

A well-organized wiki might look like this:

```
docs/
├── index.md
├── tutorials/
│   ├── beginner-guide.md
│   └── advanced-techniques.md
├── examples/
│   ├── code-samples.md
│   └── use-cases.md
└── reference/
    ├── api-docs.md
    └── glossary.md
```

### Update Navigation Structure

Organize your navigation in `mkdocs.yml`:

```yaml
nav:
  - Home: index.md
  - Tutorials:
    - Beginner Guide: tutorials/beginner-guide.md
    - Advanced Techniques: tutorials/advanced-techniques.md
  - Examples:
    - Code Samples: examples/code-samples.md
    - Use Cases: examples/use-cases.md
  - Reference:
    - API Documentation: reference/api-docs.md
    - Glossary: reference/glossary.md
```

## Step 5: Build and Test

### Local Testing

Before sharing your changes, test them locally:

```bash
# Serve locally with live reload
mkdocs serve

# Build the static site
mkdocs build

# Build with strict mode (catches more errors)
mkdocs build --strict
```

### Validation Checklist

Before committing your changes:

- [ ] All pages load without errors
- [ ] Navigation links work correctly
- [ ] Images and assets load properly
- [ ] Search functionality works
- [ ] Mobile view looks good
- [ ] No broken internal links

## Step 6: Deploy to GitHub Pages

### Automatic Deployment

If you're using GitHub, you can set up automatic deployment:

1. **Push your changes** to the main branch
2. **GitHub Actions** will build and deploy automatically (if configured)
3. **View your live site** at `https://your-username.github.io/wikifruity`

### Manual Deployment

You can also deploy manually:

```bash
# Deploy to GitHub Pages
mkdocs gh-deploy
```

This command:
- Builds the site
- Creates/updates the `gh-pages` branch
- Pushes the built site to GitHub Pages

## Common Workflows

### Adding a New Article

1. Create the markdown file in the appropriate directory
2. Write your content using markdown
3. Add the page to navigation in `mkdocs.yml`
4. Test locally with `mkdocs serve`
5. Commit and push your changes

### Updating Existing Content

1. Find the markdown file you want to edit
2. Make your changes
3. Preview them locally
4. Commit and push

### Adding Images

1. Create an `images` or `assets` directory in `docs/`
2. Add your image files
3. Reference them in markdown: `![Alt text](images/your-image.png)`

## 🎉 Congratulations!

You've successfully completed the WikiFruity quick start! You now know how to:

- ✅ Edit existing pages
- ✅ Create new pages and organize content
- ✅ Use advanced markdown features
- ✅ Test changes locally
- ✅ Deploy to GitHub Pages

## What's Next?

Now that you've mastered the basics, explore these areas:

1. **[User Guide](../user-guide/overview.md)** - Learn about advanced features
2. **[API Reference](../api/overview.md)** - Technical documentation
3. **[Contributing Guidelines](../contributing/guidelines.md)** - Help improve the wiki
4. **Material Theme Docs** - [Explore more features](https://squidfunk.github.io/mkdocs-material/)

## Need Help?

If you run into issues:

- Check the [Installation guide](installation.md) for troubleshooting
- Review the [MkDocs documentation](https://www.mkdocs.org/)
- Look at existing pages for examples
- Ask questions in the project's discussion forum

---

Happy wiki building! 🚀