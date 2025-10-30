# Contributing Guidelines

Welcome to WikiFruity! We're thrilled that you're interested in contributing to our documentation project. This guide will help you understand how to contribute effectively and make the most impact.

## 🤝 Welcome Contributors

Whether you're fixing a typo, adding new content, improving existing documentation, or developing new features, your contributions are valuable and appreciated. We believe that great documentation is built by a community of contributors with diverse backgrounds and perspectives.

## 🎯 Ways to Contribute

There are many ways you can help improve WikiFruity:

### 📝 Content Contributions
- **Write new articles** - Add documentation on topics you know well
- **Improve existing content** - Update outdated information, add examples
- **Fix errors** - Correct typos, grammar issues, or factual mistakes
- **Add translations** - Help make content accessible in other languages
- **Create tutorials** - Write step-by-step guides for common tasks

### 🛠️ Technical Contributions
- **Fix bugs** - Resolve issues with the site build or functionality
- **Improve performance** - Optimize load times and user experience
- **Add features** - Develop new plugins or extensions
- **Enhance design** - Improve the visual design and user interface
- **Update dependencies** - Keep the project up-to-date with latest versions

### 🎨 Design and UX
- **Improve navigation** - Make it easier to find information
- **Enhance accessibility** - Ensure the site works for everyone
- **Create graphics** - Design diagrams, illustrations, or icons
- **User testing** - Provide feedback on the user experience

### 🐛 Issue Reporting
- **Report bugs** - Help us identify problems
- **Suggest improvements** - Share ideas for making the wiki better
- **Request features** - Propose new functionality
- **Ask questions** - Help us understand what users need

## 🚀 Getting Started

### Prerequisites

Before contributing, make sure you have:

- **GitHub account** - For submitting contributions
- **Git installed** - For version control
- **Python 3.7+** - For running MkDocs locally
- **Basic markdown knowledge** - For content creation

### Set Up Development Environment

1. **Fork the repository**
   - Go to the WikiFruity GitHub page
   - Click "Fork" to create your copy

2. **Clone your fork**
   ```bash
   git clone https://github.com/your-username/wikifruity.git
   cd wikifruity
   ```

3. **Set up virtual environment**
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

4. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

5. **Start development server**
   ```bash
   mkdocs serve
   ```

6. **Make your changes**
   - Edit files in the `docs/` directory
   - See changes live at `http://127.0.0.1:8000`

## 📋 Contribution Process

### 1. Choose or Create an Issue

- **Browse existing issues** - Look for issues labeled "good first issue" or "help wanted"
- **Create new issues** - If you have ideas or found bugs
- **Discuss before major changes** - Comment on issues to coordinate efforts

### 2. Create a Branch

```bash
# Create and switch to a new branch
git checkout -b feature/your-feature-name

# Or for bug fixes
git checkout -b fix/issue-description
```

### 3. Make Your Changes

- **Follow our style guidelines** (see below)
- **Test your changes locally**
- **Keep commits focused and atomic**
- **Write descriptive commit messages**

### 4. Submit a Pull Request

1. **Push your branch**
   ```bash
   git push origin your-branch-name
   ```

2. **Create pull request** on GitHub
3. **Fill out the PR template** completely
4. **Link related issues** using keywords like "Fixes #123"
5. **Request review** from maintainers

### 5. Address Feedback

- **Respond to comments** promptly and professionally
- **Make requested changes** in additional commits
- **Update documentation** if your changes affect it

## 📖 Content Guidelines

### Writing Style

- **Clear and concise** - Use simple, direct language
- **Consistent tone** - Match the existing documentation style
- **Inclusive language** - Use terms that welcome all users
- **Active voice** - Prefer active over passive voice when possible
- **User-focused** - Write from the user's perspective

### Structure and Organization

- **Logical hierarchy** - Use proper heading levels (H1, H2, H3)
- **Scannable content** - Use bullet points, numbered lists, and short paragraphs
- **Consistent formatting** - Follow established patterns
- **Cross-references** - Link to related content appropriately

### Markdown Standards

- **Headers**: Use `#` for H1, `##` for H2, etc.
- **Code blocks**: Specify language for syntax highlighting
- **Links**: Use descriptive link text, not "click here"
- **Images**: Include alt text for accessibility
- **Tables**: Use proper table formatting with headers

#### Example Code Block
```python
def example_function():
    """This is a properly formatted code example."""
    return "Hello, WikiFruity!"
```

#### Example Admonition
```markdown
!!! tip "Pro Tip"
    Use admonitions to highlight important information.
```

### Content Types

#### Tutorials
- **Step-by-step format** with numbered instructions
- **Prerequisites** section at the beginning
- **Expected outcomes** clearly stated
- **Troubleshooting** section for common issues

#### Reference Documentation
- **Comprehensive coverage** of topics
- **Organized alphabetically** or logically
- **Examples provided** for complex concepts
- **Version information** when relevant

#### How-to Guides
- **Problem-focused** approach
- **Minimal background** explanation
- **Direct instructions** to solve specific issues
- **Related links** to deeper explanations

## 🔧 Technical Guidelines

### File Organization

```
docs/
├── index.md                 # Homepage content
├── getting-started/         # Beginner-focused content
├── user-guide/             # Comprehensive documentation
├── api/                    # Technical reference
├── contributing/           # This section
└── images/                 # Image assets
```

### Naming Conventions

- **File names**: Use lowercase with hyphens (`my-new-page.md`)
- **Directory names**: Use lowercase with hyphens
- **Image files**: Descriptive names with appropriate extensions
- **Branch names**: Use prefixes like `feature/`, `fix/`, `docs/`

### Configuration Changes

When modifying `mkdocs.yml`:

- **Test thoroughly** - Ensure the site builds without errors
- **Update navigation** - Add new pages to the nav section
- **Validate YAML** - Check for syntax errors
- **Document changes** - Explain why changes were made

## 🧪 Testing and Quality

### Before Submitting

- [ ] **Local testing** - Run `mkdocs serve` and check your changes
- [ ] **Build testing** - Run `mkdocs build --strict` to catch errors
- [ ] **Link checking** - Verify all links work correctly
- [ ] **Mobile testing** - Check how content looks on mobile devices
- [ ] **Accessibility** - Ensure content is accessible to all users

### Content Review Checklist

- [ ] **Spelling and grammar** - Use spell check and proofread
- [ ] **Consistency** - Matches existing style and tone
- [ ] **Accuracy** - Information is correct and up-to-date
- [ ] **Completeness** - Content thoroughly covers the topic
- [ ] **Navigation** - Page is properly linked in the navigation

## 📋 Pull Request Template

When creating a pull request, please include:

```markdown
## Description
Brief description of changes made.

## Type of Change
- [ ] Documentation update
- [ ] New content
- [ ] Bug fix
- [ ] Feature addition
- [ ] Configuration change

## Testing
- [ ] Tested locally with `mkdocs serve`
- [ ] Built successfully with `mkdocs build --strict`
- [ ] Checked on mobile devices
- [ ] Verified all links work

## Related Issues
Fixes #(issue number)

## Additional Notes
Any additional information reviewers should know.
```

## 🤖 Automation and CI/CD

### GitHub Actions

Our CI/CD pipeline automatically:

- **Builds the site** on every push and PR
- **Runs quality checks** to catch errors
- **Deploys to GitHub Pages** when changes are merged
- **Performs link checking** to find broken links

### Pre-commit Hooks

Consider setting up pre-commit hooks:

```bash
pip install pre-commit
pre-commit install
```

This will automatically check your changes before each commit.

## 🏆 Recognition

We value all contributions and recognize contributors in several ways:

- **Contributors list** - Added to project documentation
- **GitHub recognition** - Contributions appear on your GitHub profile
- **Community shout-outs** - Recognition in community channels
- **Maintainer consideration** - Active contributors may be invited as maintainers

## 📞 Getting Help

### Communication Channels

- **GitHub Issues** - For bugs, features, and general discussion
- **GitHub Discussions** - For community conversation and Q&A
- **Pull Request Comments** - For specific code/content feedback

### Mentorship

New contributors can get help from:

- **Good first issues** - Specially labeled for beginners
- **Mentorship program** - Experienced contributors willing to help
- **Documentation** - Comprehensive guides and examples
- **Community support** - Friendly and welcoming community

## 🛡️ Code of Conduct

### Our Commitment

We are committed to providing a welcoming, inclusive, and harassment-free experience for everyone, regardless of:

- Age, body size, disability, ethnicity, gender identity and expression
- Level of experience, nationality, personal appearance, race, religion
- Sexual identity and orientation, socioeconomic status

### Expected Behavior

- **Be respectful** - Treat everyone with kindness and respect
- **Be collaborative** - Work together constructively
- **Be patient** - Help others learn and grow
- **Be inclusive** - Welcome people from all backgrounds
- **Be professional** - Maintain appropriate standards of conduct

### Unacceptable Behavior

- **Harassment** - Intimidation, stalking, or unwanted attention
- **Discrimination** - Exclusion based on protected characteristics
- **Trolling** - Deliberately inflammatory or disruptive behavior
- **Spam** - Irrelevant or promotional content
- **Doxxing** - Publishing private information without permission

### Reporting Issues

If you experience or witness unacceptable behavior:

1. **Document the incident** - Save relevant information
2. **Report to maintainers** - Contact project maintainers privately
3. **Expect investigation** - We will investigate all reports
4. **Await resolution** - Appropriate action will be taken

## 🎓 Learning Resources

### MkDocs and Material Theme

- [MkDocs Documentation](https://www.mkdocs.org/)
- [Material Theme Guide](https://squidfunk.github.io/mkdocs-material/)
- [Python-Markdown Documentation](https://python-markdown.github.io/)

### Markdown and Writing

- [Markdown Guide](https://www.markdownguide.org/)
- [Google Developer Documentation Style Guide](https://developers.google.com/style)
- [GitLab Documentation Style Guide](https://docs.gitlab.com/ee/development/documentation/styleguide/)

### Git and GitHub

- [Git Handbook](https://guides.github.com/introduction/git-handbook/)
- [GitHub Flow](https://guides.github.com/introduction/flow/)
- [Contributing to Open Source](https://opensource.guide/how-to-contribute/)

## 📊 Project Statistics and Health

We track several metrics to ensure project health:

- **Contributor activity** - Number of active contributors
- **Issue resolution** - Time to resolve issues and PRs
- **Content freshness** - Regular updates and maintenance
- **User feedback** - Community satisfaction and suggestions

## 🎉 Thank You

Thank you for taking the time to contribute to WikiFruity! Your efforts help create better documentation for everyone. Whether you're fixing a typo, writing a comprehensive guide, or developing new features, every contribution makes a difference.

We look forward to collaborating with you and seeing what amazing things we can build together!

---

*Happy contributing! 🚀*

For questions about these guidelines, please [open an issue](https://github.com/your-username/wikifruity/issues) or reach out to the maintainers.