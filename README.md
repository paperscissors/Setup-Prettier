# Prettier Setup Script for JS Projects

A Python script to automatically configure Prettier, ESLint, and Git pre-commit hooks in Vue.js and other JS projects.

## Features

- Detects and uses existing package manager (npm/yarn)
- Installs required dependencies
- Creates/updates configuration files
- Sets up Git pre-commit hooks with husky
- Preserves existing configurations while adding Prettier settings
- Handles both new and existing projects

## Installation

```bash
# Clone or download the script
curl -o ~/bin/setup_prettier.py https://raw.githubusercontent.com/paperscissors/Setup-Prettier/setup_prettier.py

# Make it executable
chmod +x ~/bin/setup_prettier.py

# Create symlink (optional)
ln -s ~/bin/setup_prettier.py /usr/local/bin/setup_prettier
```

## Usage

```bash
setup_prettier <project_directory>

# Example for current directory
setup_prettier .
```

## What It Does

1. **Package Installation**
   - prettier
   - @vue/eslint-config-prettier
   - eslint-plugin-prettier
   - husky
   - lint-staged

2. **Configuration Files**
   - Creates `.prettierrc` with Vue-optimized settings
   - Creates `.prettierignore`
   - Updates `.eslintrc.json` (or similar)
   - Updates `package.json` scripts and lint-staged config

3. **Git Hooks**
   - Sets up husky
   - Configures pre-commit hook to run prettier

## Configuration Details

### Prettier Configuration
```json
{
  "semi": false,
  "tabWidth": 2,
  "singleQuote": true,
  "printWidth": 80,
  "trailingComma": "es5",
  "vueIndentScriptAndStyle": true
}
```

### ESLint Integration
```json
{
  "extends": ["plugin:prettier/recommended"],
  "plugins": ["prettier"],
  "rules": {
    "prettier/prettier": "error",
    "vue/multi-word-component-names": ["error", {
      "ignores": ["Game", "Play"]
    }]
  }
}
```

## Requirements

- Python 3.6+
- npm or yarn
- Git repository initialized

## Troubleshooting

1. **Permission Errors**
   ```bash
   chmod +x setup_prettier.py
   ```

2. **Package Manager Errors**
   - Ensure package.json exists
   - Check write permissions

3. **Git Hook Errors**
   - Ensure Git is initialized
   - Check husky installation
