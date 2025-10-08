# Contributing to IESCP

First off, thank you for considering contributing to IESCP! It's people like you that make IESCP such a great tool.

## Code of Conduct

This project and everyone participating in it is governed by our commitment to providing a welcoming and inspiring community for all.

## How Can I Contribute?

### Reporting Bugs

Before creating bug reports, please check the existing issues as you might find out that you don't need to create one. When you are creating a bug report, please include as many details as possible:

* **Use a clear and descriptive title** for the issue to identify the problem.
* **Describe the exact steps which reproduce the problem** in as many details as possible.
* **Provide specific examples to demonstrate the steps**.
* **Describe the behavior you observed after following the steps** and point out what exactly is the problem with that behavior.
* **Explain which behavior you expected to see instead and why.**
* **Include screenshots and animated GIFs** if possible.

### Suggesting Enhancements

Enhancement suggestions are tracked as GitHub issues. When creating an enhancement suggestion, please include:

* **Use a clear and descriptive title** for the issue to identify the suggestion.
* **Provide a step-by-step description of the suggested enhancement** in as many details as possible.
* **Provide specific examples to demonstrate the steps** or point out the part of IESCP where the suggestion is related to.
* **Describe the current behavior** and **explain which behavior you expected to see instead** and why.
* **Explain why this enhancement would be useful** to most IESCP users.

### Pull Requests

* Fill in the required template
* Do not include issue numbers in the PR title
* Follow the Python style guide (PEP 8)
* Include thoughtfully-worded, well-structured tests
* Document new code
* End all files with a newline

## Development Process

1. **Fork the repository** and create your branch from `main`.
2. **Install dependencies**: `pip install -r requirement.txt`
3. **Make your changes** in your branch
4. **Test your changes** thoroughly
5. **Commit your changes** with clear commit messages
6. **Push to your fork** and submit a pull request

## Styleguides

### Git Commit Messages

* Use the present tense ("Add feature" not "Added feature")
* Use the imperative mood ("Move cursor to..." not "Moves cursor to...")
* Limit the first line to 72 characters or less
* Reference issues and pull requests liberally after the first line
* Consider starting the commit message with an applicable emoji:
    * 🎨 `:art:` when improving the format/structure of the code
    * 🐎 `:racehorse:` when improving performance
    * 📝 `:memo:` when writing docs
    * 🐛 `:bug:` when fixing a bug
    * 🔥 `:fire:` when removing code or files
    * ✅ `:white_check_mark:` when adding tests
    * 🔒 `:lock:` when dealing with security
    * ⬆️ `:arrow_up:` when upgrading dependencies
    * ⬇️ `:arrow_down:` when downgrading dependencies

### Python Styleguide

All Python code must adhere to [PEP 8](https://www.python.org/dev/peps/pep-0008/).

Key points:
* Use 4 spaces for indentation (not tabs)
* Limit all lines to a maximum of 79 characters
* Use docstrings for all public modules, functions, classes, and methods
* Use meaningful variable names
* Add comments for complex logic

### HTML/CSS Styleguide

* Use 2 spaces for indentation in HTML/CSS
* Use lowercase for HTML tags and attributes
* Use meaningful class names
* Keep CSS organized by component

### Flask Route Conventions

* Use clear, RESTful route names
* Group related routes together
* Add docstrings explaining route purpose
* Include proper error handling
* Validate user input

## Testing

* Write tests for new features
* Ensure all tests pass before submitting PR
* Test on different browsers if UI changes are made
* Test with different user roles (Admin, Sponsor, Influencer)

## Database Changes

If your contribution involves database schema changes:

1. Update the models in `models.py`
2. Create migration scripts if using Flask-Migrate
3. Document the changes in your PR
4. Ensure backward compatibility when possible

## Documentation

* Update README.md if needed
* Add inline comments for complex code
* Update API documentation for new routes
* Include examples in docstrings

## Community

* Be respectful and constructive
* Help others in issues and discussions
* Share your knowledge
* Celebrate successes together

## Questions?

Feel free to open an issue with your question or reach out to the maintainers.

---

Thank you for contributing to IESCP! 🎉
