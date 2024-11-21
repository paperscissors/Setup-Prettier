# Prettier Setup Script for JavaScript Projects

A Python script that automatically configures Prettier, ESLint, and Git pre-commit hooks for JavaScript projects, with special handling for Vue.js and React.

## Features

- Auto-detects project type (Vue/React/vanilla JS)
- Uses existing package manager (npm/yarn)
- Installs required dependencies
- Creates/updates configuration files
- Sets up Git pre-commit hooks with husky
- Framework-specific optimizations

## Installation

```bash
# copy to a location in your path from https://raw.githubusercontent.com/paperscissors/Setup-Prettier/setup_prettier.py
# make sure it's executable

```

## Usage

```bash
setup_prettier <project_directory>
```

## What It Does

1. **Auto-Detection**
   - Project type (Vue/React/JS)
   - Package manager (npm/yarn)

2. **Package Installation**
   - prettier
   - eslint-plugin-prettier
   - Framework-specific ESLint configs
   - husky
   - lint-staged

3. **Configuration Files**
   - `.prettierrc` with framework optimizations
   - `.prettierignore`
   - `.eslintrc.json`
   - `package.json` scripts and lint-staged config

4. **Git Hooks**
   - husky pre-commit setup
   - lint-staged configuration

## Framework-Specific Features

### Vue.js
- Vue template indentation
- Component name rules
- Vue-specific ESLint config

### React
- JSX formatting
- React-specific ESLint config

### Vanilla JavaScript
- Basic JS/TS formatting
- General ESLint setup

## Requirements

- Python 3.6+
- npm or yarn
- Git repository initialized

## Troubleshooting

1. **Permission Issues**
   ```bash
   chmod +x setup_prettier.py
   ```

2. **Package Manager Errors**
   - Verify package.json exists
   - Check write permissions

3. **Git Hook Errors**
   - Ensure Git is initialized
   - Verify husky installation
