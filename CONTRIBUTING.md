# 🤝 Contributing to Skylite UX

Thank you for your interest in contributing to Skylite UX! We welcome contributions from the community and appreciate your help in making this project better.

## 📋 Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How Can I Contribute?](#how-can-i-contribute)
- [Development Process](#development-process)
- [Pull Request Guidelines](#pull-request-guidelines)
- [Code Style Guidelines](#code-style-guidelines)
- [Commit Message Guidelines](#commit-message-guidelines)
- [Reporting Bugs](#reporting-bugs)
- [Suggesting Enhancements](#suggesting-enhancements)
- [Questions and Discussions](#questions-and-discussions)

## 📜 Code of Conduct

This project and everyone participating in it is governed by our Code of Conduct. By participating, you are expected to uphold this code.

### Our Standards

- **Be respectful** - Treat everyone with respect and dignity
- **Be inclusive** - Welcome people of all backgrounds and experience levels
- **Be collaborative** - Work together to achieve common goals
- **Be constructive** - Provide helpful, constructive feedback
- **Be patient** - Understand that everyone has different schedules and priorities

### Unacceptable Behavior

- Harassment, discrimination, or offensive behavior
- Trolling, insulting, or derogatory comments
- Publishing others' private information without permission
- Other conduct that could reasonably be considered inappropriate

## 🎯 How Can I Contribute?

There are many ways to contribute to Skylite UX:

### 🐛 Bug Reports
- Report bugs you encounter
- Help reproduce and verify bug fixes
- Test bug fixes in different environments

### 💡 Feature Requests
- Suggest new features
- Discuss feature implementations
- Help prioritize features

### 📝 Documentation
- Improve existing documentation
- Write tutorials and guides
- Translate documentation
- Fix typos and grammar

### 🔧 Code Contributions
- Fix bugs
- Implement new features
- Improve performance
- Add tests
- Refactor code

### 🧪 Testing
- Write unit tests
- Write integration tests
- Test on different platforms
- Report test results

### 🎨 Design
- Improve UI/UX
- Create mockups
- Provide design feedback
- Help with accessibility

## 🔄 Development Process

### 1. Choose an Issue

- Check the [Issues](https://github.com/your-username/Skylite-UX/issues) page
- Look for issues labeled:
  - `good first issue` - Great for beginners
  - `help wanted` - Issues that need help
  - `bug` - Bug fixes
  - `enhancement` - New features

### 2. Comment on the Issue

- Comment on the issue you want to work on
- Let others know you're working on it
- Ask questions if you need clarification

### 3. Make Your Changes

- Follow the [Code Style Guidelines](#code-style-guidelines)
- Write tests for new features
- Update documentation as needed
- Test your changes thoroughly

### 4. Commit Your Changes

- Follow the [Commit Message Guidelines](#commit-message-guidelines)
- Make small, focused commits
- Include tests with your changes

### 5. Push and Create a Pull Request

```bash
git push origin feature/your-feature-name
```

Then create a Pull Request on GitHub.

## 📋 Pull Request Guidelines

### Before Submitting

- [ ] Code follows the style guidelines
- [ ] Self-review your code
- [ ] Add tests for new functionality
- [ ] Update documentation
- [ ] Ensure all tests pass
- [ ] Check for any linting errors

### Pull Request Template

When creating a Pull Request, use this template:

```markdown
## Description
Brief description of what this PR does.

## Type of Change
- [ ] Bug fix (non-breaking change which fixes an issue)
- [ ] New feature (non-breaking change which adds functionality)
- [ ] Breaking change (fix or feature that would cause existing functionality to not work as expected)
- [ ] Documentation update

## Testing
- [ ] I have tested this change locally
- [ ] I have added tests that prove my fix is effective or that my feature works
- [ ] All existing tests pass

## Checklist
- [ ] My code follows the style guidelines of this project
- [ ] I have performed a self-review of my own code
- [ ] I have commented my code, particularly in hard-to-understand areas
- [ ] I have made corresponding changes to the documentation
- [ ] My changes generate no new warnings
- [ ] I have added tests that prove my fix is effective or that my feature works
- [ ] New and existing unit tests pass locally with my changes

## Screenshots (if applicable)
Add screenshots to help explain your changes.

## Additional Notes
Any additional information or context.
```

### Review Process

1. **Automated Checks** - CI/CD will run tests and linting
2. **Code Review** - Maintainers will review your code
3. **Feedback** - You may receive feedback and requested changes
4. **Approval** - Once approved, your PR will be merged

## 📝 Code Style Guidelines

### General Principles

- **Readability** - Write code that's easy to read and understand
- **Consistency** - Follow existing patterns in the codebase
- **Simplicity** - Keep things simple and avoid over-engineering
- **Documentation** - Comment complex logic and public APIs

### TypeScript

- Use TypeScript for all new code
- Define proper types for all variables and functions
- Use interfaces for object shapes
- Avoid `any` type when possible

```typescript
// Good
interface User {
  id: string
  name: string
  email: string
}

const getUser = (id: string): Promise<User> => {
  // implementation
}

// Avoid
const getUser = (id: any): any => {
  // implementation
}
```

### Vue.js

- Use Composition API for new components
- Use `<script setup>` syntax when possible
- Follow Vue.js naming conventions
- Use proper prop validation

```vue
<script setup lang="ts">
interface Props {
  title: string
  count?: number
}

const props = withDefaults(defineProps<Props>(), {
  count: 0
})

const emit = defineEmits<{
  update: [value: string]
}>()
</script>
```

### CSS/Styling

- Use Tailwind CSS for styling
- Follow utility-first approach
- Use CSS custom properties for theming
- Ensure responsive design

```vue
<template>
  <div class="flex items-center justify-between p-4 bg-white rounded-lg shadow-sm">
    <h2 class="text-lg font-semibold text-gray-900">{{ title }}</h2>
    <button class="px-4 py-2 text-sm font-medium text-white bg-blue-600 rounded-md hover:bg-blue-700">
      Action
    </button>
  </div>
</template>
```

## 💬 Commit Message Guidelines

We follow the [Conventional Commits](https://www.conventionalcommits.org/) specification.

### Format

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

### Types

- **feat**: A new feature
- **fix**: A bug fix
- **docs**: Documentation only changes
- **style**: Changes that do not affect the meaning of the code
- **refactor**: A code change that neither fixes a bug nor adds a feature
- **perf**: A code change that improves performance
- **test**: Adding missing tests or correcting existing tests
- **chore**: Changes to the build process or auxiliary tools

### Examples

```bash
feat: add user authentication system
fix(auth): resolve login redirect issue
docs: update installation instructions
style: format code with prettier
refactor(components): extract reusable button component
test: add unit tests for user service
chore: update dependencies
```

## 🐛 Reporting Bugs

### Before Reporting

- Check if the bug has already been reported
- Try to reproduce the bug consistently
- Check if it's a configuration issue

### Bug Report Template

```markdown
## Bug Description
Clear and concise description of the bug.

## Steps to Reproduce
1. Go to '...'
2. Click on '...'
3. Scroll down to '...'
4. See error

## Expected Behavior
What you expected to happen.

## Actual Behavior
What actually happened.

## Environment
- Host OS: [e.g. Linux fork, NAS type, etc...]
- Client OS: [e.g. Android, Raspberry Pi OS, etc...]
- Browser: [e.g. Chrome, Firefox]

## Additional Context
Add any other context about the problem here.

## Screenshots
If applicable, add screenshots to help explain your problem.
```

## 💡 Suggesting Enhancements

### Before Suggesting

- Check if the feature has already been requested
- Think about the use case and benefits
- Consider implementation complexity

### Enhancement Request Template

```markdown
## Problem Statement
Is your feature request related to a problem? Please describe.

## Proposed Solution
A clear and concise description of what you want to happen.

## Alternative Solutions
A clear and concise description of any alternative solutions you've considered.

## Additional Context
Add any other context or screenshots about the feature request here.

## Use Cases
Describe specific use cases where this feature would be helpful.
```

## ❓ Questions and Discussions

### Getting Help

- **GitHub Discussions**: Use the [Discussions](https://github.com/wetzel402/Skylite-UX/discussions) tab for questions
- **Discord**: Join our [Discord server](https://discord.gg/KJn3YfWxn7) for real-time help
- **Issues**: Use issues for bug reports and feature requests only

### Asking Good Questions

- Provide context about your environment
- Include error messages and logs
- Show what you've already tried
- Be specific about what you're trying to achieve

## 🏆 Recognition

Contributors will be recognized in several ways:

- **Release notes** for significant contributions
- **Special thanks** for major contributions
- **Maintainer status** for consistent contributors

## 📞 Contact

If you have any questions about contributing:

- **Discord**: [Join our server](https://discord.gg/KJn3YfWxn7)
- **GitHub Issues**: [Create an issue](https://github.com/your-username/Skylite-UX/issues)

---

<div align="center">
  <sub>Thank you for contributing to Skylite UX! 🚀</sub>
</div> 