# 🛠️ Development Guide

Welcome to the Skylite UX development guide! This document will help you set up your development environment and understand the project structure.

## 📋 Table of Contents

- [Prerequisites](#prerequisites)
- [Quick Start](#quick-start)
- [Project Structure](#project-structure)
- [Development Workflow](#development-workflow)
- [Testing](#testing)
- [Building](#building)
- [Troubleshooting](#troubleshooting)

## 🔧 Prerequisites

Before you begin, ensure you have the following installed:

- [Docker](https://docs.docker.com/get-started/get-docker/)
- [Visual Studio Code](https://code.visualstudio.com/)

## 🚀 Quick Start

- Fork the repo and create your feature branch from `dev`.
 - Install [Docker](https://docs.docker.com/get-started/get-docker/) 
 - Install [Visual Studio Code](https://code.visualstudio.com/)
 - In VScode [open the command palette and select](https://code.visualstudio.com/docs/devcontainers/containers#_quick-start-open-a-git-repository-or-github-pr-in-an-isolated-container-volume) `Dev Containers: Clone Repository in Container Volume`. Select your repository and branch. 
 - Start the development server on `http://localhost:3000` with:

```bash
# npm
npm run dev
```

## 📁 Project Structure

```
Skylite-UX/
├── .devcontainer/           # Dev container configuration
│   └── integrations/        # Compose files to deploy integration containers
├── app/                     # Main application code
│   ├── assets/              # Static assets (CSS, images, etc.)
│   ├── components/          # Vue components
│   │   ├── calendar/        # Calendar-related components
│   │   ├── global/          # Global/shared components
│   │   ├── settings/        # Settings page components
│   │   ├── shopping/        # Shopping list components
│   │   └── todos/           # Todo list components
│   ├── composables/         # Vue composables
│   ├── integrations/        # External service integration files
│   ├── lib/                 # Library configurations
│   ├── pages/               # Application pages (auto-routed)
│   ├── plugins/             # Nuxt plugins
│   ├── types/               # TypeScript type definitions
│   ├── utils/               # Utility functions
│   ├── app.config.ts        # App configuration
│   └── app.vue              # Root Vue component
├── prisma/                  # Database schema and migrations
│   ├── migrations/          # Database migration files
│   └── schema.prisma        # Prisma schema definition
├── public/                  # Public static assets
├── server/                  # Server-side code
│   ├── api/                 # API endpoints
│   │   ├── integrations/    # Integration API routes
│   │   ├── shopping-lists/  # Shopping list API routes
│   │   ├── todos/           # Todo API routes
│   │   └── users/           # User API routes
│   ├── plugins/             # Server plugins
│   └── utils/               # Server utility functions
├── eslint.config.mjs        # ESLint configuration
├── LICENSE.md               # Project license
├── nuxt.config.ts           # Nuxt configuration
├── package.json             # Dependencies and scripts
├── README.md                # Project documentation
└── tsconfig.json            # TypeScript configuration
``` 

## 🔄 Development Workflow

### 1. Branch Strategy

- **main**: Production-ready code
- **dev**: Development branch (default for PRs)
- **feature/***: New features
- **bugfix/***: Bug fixes
- **hotfix/***: Critical production fixes

### 2. Development Process

1. **Create a branch**
   ```bash
   git checkout dev
   git pull origin dev
   git checkout -b feature/your-feature-name
   ```

2. **Make your changes**
   - Write code following the style guide
   - Add tests for new features
   - Update documentation (if required)

3. **Test your changes**
   ```bash
   npm run test
   npm run lint
   npm run type-check
   ```

4. **Commit your changes**
   ```bash
   git add .
   git commit -m "feat: add new feature description"
   ```

5. **Push and create PR**
   ```bash
   git push origin feature/your-feature-name
   # Create Pull Request to dev branch
   ```

### 3. Code Style

- Use **TypeScript** for all new code
- Follow **Vue 3 Composition API** patterns
- Use **Tailwind CSS** for styling
- Follow **ESLint** and **Prettier** rules
- Write meaningful commit messages

## 🧪 Testing

### Running Tests

```bash
# Run all tests
npm run test

# Run tests in watch mode
npm run test:watch

# Run tests with coverage
npm run test:coverage

# Run specific test file
npm run test:unit components/MyComponent.test.ts
```

### Writing Tests

- Use **Vitest** for unit testing
- Use **@vue/test-utils** for component testing
- Write tests for all new features
- Aim for >80% code coverage

### Example Test

```typescript
import { describe, it, expect } from 'vitest'
import { mount } from '@vue/test-utils'
import MyComponent from '~/components/MyComponent.vue'

describe('MyComponent', () => {
  it('renders correctly', () => {
    const wrapper = mount(MyComponent)
    expect(wrapper.exists()).toBe(true)
  })
})
```

## 🏗️ Building

### Development Build

```bash
npm run build:dev
```

### Production Build

```bash
npm run build
```

### Preview Production Build

```bash
npm run preview
```

### Docker Build

```bash
# Build Docker image
docker build -t skylite-ux .

# Run Docker container
docker run -p 3000:3000 skylite-ux
```

## 🔍 Troubleshooting

### Common Issues

#### Port Already in Use
```bash
# Find process using port 3000
lsof -i :3000

# Kill the process
kill -9 <PID>
```

#### Node Modules Issues
```bash
# Clear npm cache
npm cache clean --force

# Remove node_modules and reinstall
rm -rf node_modules package-lock.json
npm install
```

#### Docker Issues
```bash
# Clean up Docker containers
docker system prune -a

# Rebuild without cache
docker-compose build --no-cache
```

#### TypeScript Errors
```bash
# Check TypeScript configuration
npm run type-check

# Regenerate TypeScript types
npm run types:generate
```

### Getting Help

- Check the [Issues](https://github.com/your-username/Skylite-UX/issues) page
- Search existing discussions
- Create a new issue with detailed information
- Join our [Discord](https://discord.gg/KJn3YfWxn7) for real-time help

## 📚 Additional Resources

- [Nuxt Documentation](https://nuxt.com/docs)
- [Vue Documentation](https://vuejs.org/)
- [Tailwind CSS Documentation](https://tailwindcss.com/docs)
- [TypeScript Documentation](https://www.typescriptlang.org/docs/)
- [Vitest Documentation](https://vitest.dev/)

---

<div align="center">
  <sub>Happy coding! 🚀</sub>
</div> 