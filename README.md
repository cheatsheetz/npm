# npm Cheat Sheet

Essential npm commands for Node.js package management and development workflow.

---

## Table of Contents
- [Basic Commands](#basic-commands)
- [Package Installation](#package-installation)
- [Package Management](#package-management)
- [npm Scripts](#npm-scripts)
- [Publishing Packages](#publishing-packages)
- [Version Management](#version-management)
- [npm Configuration](#npm-configuration)
- [Cache Management](#cache-management)
- [Security Audit](#security-audit)
- [Workspaces](#workspaces)
- [Advanced Operations](#advanced-operations)

---

## Basic Commands

| Command | Description | Example |
|---------|-------------|---------|
| `npm --version` | Show npm version | `npm --version` |
| `npm help` | Show help | `npm help` |
| `npm help <command>` | Get help for specific command | `npm help install` |
| `npm init` | Initialize new package | `npm init` |
| `npm init -y` | Initialize with defaults | `npm init -y` |
| `npm init <template>` | Initialize with template | `npm init react-app my-app` |

## Package Installation

### Basic Installation
| Command | Description | Example |
|---------|-------------|---------|
| `npm install` | Install all dependencies | `npm install` |
| `npm i` | Shorthand for install | `npm i` |
| `npm install <package>` | Install package | `npm install express` |
| `npm install <package>@<version>` | Install specific version | `npm install express@4.18.0` |
| `npm install <package>@latest` | Install latest version | `npm install express@latest` |

### Installation Types
| Command | Description | Example |
|---------|-------------|---------|
| `npm install <package>` | Install as dependency | `npm install express` |
| `npm install --save <package>` | Install as dependency (explicit) | `npm install --save express` |
| `npm install --save-dev <package>` | Install as dev dependency | `npm install --save-dev jest` |
| `npm install -D <package>` | Shorthand for dev dependency | `npm install -D nodemon` |
| `npm install --global <package>` | Install globally | `npm install --global typescript` |
| `npm install -g <package>` | Shorthand for global | `npm install -g create-react-app` |
| `npm install --save-optional <package>` | Install as optional dependency | `npm install --save-optional sharp` |
| `npm install --save-peer <package>` | Install as peer dependency | `npm install --save-peer react` |

### Installation Options
| Command | Description | Example |
|---------|-------------|---------|
| `npm install --production` | Install only production dependencies | `npm install --production` |
| `npm install --only=dev` | Install only dev dependencies | `npm install --only=dev` |
| `npm install --force` | Force install (ignore conflicts) | `npm install --force` |
| `npm install --legacy-peer-deps` | Use legacy peer dependency algorithm | `npm install --legacy-peer-deps` |
| `npm ci` | Clean install (faster, for CI) | `npm ci` |

## Package Management

### Listing Packages
| Command | Description | Example |
|---------|-------------|---------|
| `npm list` | List installed packages | `npm list` |
| `npm ls` | Shorthand for list | `npm ls` |
| `npm list --depth=0` | List top-level packages only | `npm list --depth=0` |
| `npm list --global` | List global packages | `npm list --global` |
| `npm list -g --depth=0` | List global packages (top-level) | `npm list -g --depth=0` |
| `npm outdated` | Show outdated packages | `npm outdated` |
| `npm outdated --global` | Show outdated global packages | `npm outdated --global` |

### Updating Packages
| Command | Description | Example |
|---------|-------------|---------|
| `npm update` | Update all packages | `npm update` |
| `npm update <package>` | Update specific package | `npm update express` |
| `npm update --global` | Update all global packages | `npm update --global` |
| `npm update -g <package>` | Update specific global package | `npm update -g typescript` |
| `npm install <package>@latest` | Update to latest version | `npm install express@latest` |

### Uninstalling Packages
| Command | Description | Example |
|---------|-------------|---------|
| `npm uninstall <package>` | Remove package | `npm uninstall express` |
| `npm uninstall --save <package>` | Remove from dependencies | `npm uninstall --save express` |
| `npm uninstall --save-dev <package>` | Remove from dev dependencies | `npm uninstall --save-dev jest` |
| `npm uninstall -D <package>` | Shorthand for dev removal | `npm uninstall -D nodemon` |
| `npm uninstall --global <package>` | Remove global package | `npm uninstall --global typescript` |
| `npm uninstall -g <package>` | Shorthand for global removal | `npm uninstall -g create-react-app` |

## npm Scripts

### Running Scripts
| Command | Description | Example |
|---------|-------------|---------|
| `npm run <script>` | Run custom script | `npm run build` |
| `npm start` | Run start script | `npm start` |
| `npm test` | Run test script | `npm test` |
| `npm run test` | Explicit test run | `npm run test` |
| `npm run <script> -- <args>` | Pass arguments to script | `npm run test -- --watch` |

### Script Management
| Command | Description | Example |
|---------|-------------|---------|
| `npm run` | List available scripts | `npm run` |
| `npm run-script` | Alternative to npm run | `npm run-script build` |

### Common package.json Scripts
```json
{
  "scripts": {
    "start": "node server.js",
    "dev": "nodemon server.js",
    "build": "webpack --mode=production",
    "test": "jest",
    "test:watch": "jest --watch",
    "lint": "eslint src/",
    "lint:fix": "eslint src/ --fix",
    "clean": "rm -rf dist/",
    "prebuild": "npm run clean",
    "postinstall": "node scripts/setup.js",
    "serve": "serve -s dist/",
    "format": "prettier --write src/"
  }
}
```

## Publishing Packages

### Registry Management
| Command | Description | Example |
|---------|-------------|---------|
| `npm login` | Login to npm registry | `npm login` |
| `npm logout` | Logout from npm registry | `npm logout` |
| `npm whoami` | Show current user | `npm whoami` |
| `npm adduser` | Add new user account | `npm adduser` |

### Publishing
| Command | Description | Example |
|---------|-------------|---------|
| `npm publish` | Publish package | `npm publish` |
| `npm publish --access public` | Publish public scoped package | `npm publish --access public` |
| `npm publish --tag beta` | Publish with tag | `npm publish --tag beta` |
| `npm publish --dry-run` | Test publish without actually publishing | `npm publish --dry-run` |
| `npm unpublish <package>@<version>` | Unpublish specific version | `npm unpublish my-package@1.0.0` |

### Package Information
| Command | Description | Example |
|---------|-------------|---------|
| `npm view <package>` | View package information | `npm view express` |
| `npm show <package>` | Alias for view | `npm show express` |
| `npm info <package>` | Alias for view | `npm info express` |
| `npm view <package> versions` | View all versions | `npm view express versions` |
| `npm view <package> version` | View latest version | `npm view express version` |
| `npm search <query>` | Search for packages | `npm search react router` |

## Version Management

### Version Commands
| Command | Description | Example |
|---------|-------------|---------|
| `npm version` | Show current version | `npm version` |
| `npm version patch` | Increment patch version | `npm version patch` |
| `npm version minor` | Increment minor version | `npm version minor` |
| `npm version major` | Increment major version | `npm version major` |
| `npm version prerelease` | Increment prerelease version | `npm version prerelease` |
| `npm version <version>` | Set specific version | `npm version 1.2.3` |

### Version Options
| Command | Description | Example |
|---------|-------------|---------|
| `npm version patch --no-git-tag-version` | Version without git tag | `npm version patch --no-git-tag-version` |
| `npm version patch -m "Release %s"` | Custom commit message | `npm version patch -m "Release %s"` |

### Semantic Versioning
```
Major.Minor.Patch (e.g., 1.2.3)
- Major: Breaking changes
- Minor: New features (backward compatible)
- Patch: Bug fixes (backward compatible)

Prerelease: 1.2.3-alpha.1, 1.2.3-beta.2, 1.2.3-rc.1
```

## npm Configuration

### Configuration Commands
| Command | Description | Example |
|---------|-------------|---------|
| `npm config list` | Show all config | `npm config list` |
| `npm config list -l` | Show all config (long) | `npm config list -l` |
| `npm config get <key>` | Get config value | `npm config get registry` |
| `npm config set <key> <value>` | Set config value | `npm config set registry https://registry.npmjs.org/` |
| `npm config delete <key>` | Delete config value | `npm config delete proxy` |
| `npm config edit` | Edit config file | `npm config edit` |

### Common Configuration
| Command | Description | Example |
|---------|-------------|---------|
| `npm config set registry <url>` | Set registry URL | `npm config set registry https://npm.company.com/` |
| `npm config set proxy <url>` | Set HTTP proxy | `npm config set proxy http://proxy.company.com:8080` |
| `npm config set https-proxy <url>` | Set HTTPS proxy | `npm config set https-proxy http://proxy.company.com:8080` |
| `npm config set save-exact true` | Save exact versions | `npm config set save-exact true` |
| `npm config set init-author-name "Name"` | Set default author | `npm config set init-author-name "John Doe"` |
| `npm config set init-license "MIT"` | Set default license | `npm config set init-license "MIT"` |

### Configuration Files
```bash
# Global config
~/.npmrc

# Project config
/path/to/project/.npmrc

# Example .npmrc
registry=https://registry.npmjs.org/
save-exact=true
init-author-name=John Doe
init-license=MIT
```

## Cache Management

| Command | Description | Example |
|---------|-------------|---------|
| `npm cache verify` | Verify cache integrity | `npm cache verify` |
| `npm cache clean --force` | Clear cache | `npm cache clean --force` |
| `npm cache ls` | List cache contents | `npm cache ls` |
| `npm cache add <package>` | Add package to cache | `npm cache add express` |

## Security Audit

### Audit Commands
| Command | Description | Example |
|---------|-------------|---------|
| `npm audit` | Run security audit | `npm audit` |
| `npm audit fix` | Auto-fix vulnerabilities | `npm audit fix` |
| `npm audit fix --force` | Force fix (may break changes) | `npm audit fix --force` |
| `npm audit --json` | Audit in JSON format | `npm audit --json` |
| `npm audit --audit-level moderate` | Set audit level | `npm audit --audit-level moderate` |

### Audit Levels
- `low`: Show low severity and above
- `moderate`: Show moderate severity and above
- `high`: Show high severity and above
- `critical`: Show critical severity only

## Workspaces

### Workspace Setup
```json
{
  "name": "my-monorepo",
  "workspaces": [
    "packages/*",
    "apps/*"
  ]
}
```

### Workspace Commands
| Command | Description | Example |
|---------|-------------|---------|
| `npm install` | Install all workspace dependencies | `npm install` |
| `npm run <script> --workspaces` | Run script in all workspaces | `npm run test --workspaces` |
| `npm run <script> --workspace=<name>` | Run script in specific workspace | `npm run build --workspace=package-a` |
| `npm install <package> -w <workspace>` | Install to specific workspace | `npm install express -w server` |
| `npm list --workspaces` | List all workspace dependencies | `npm list --workspaces` |

## Advanced Operations

### Package Linking
| Command | Description | Example |
|---------|-------------|---------|
| `npm link` | Create global link | `npm link` |
| `npm link <package>` | Link to local package | `npm link my-package` |
| `npm unlink <package>` | Unlink package | `npm unlink my-package` |

### Package Information
| Command | Description | Example |
|---------|-------------|---------|
| `npm ls <package>` | Find package in tree | `npm ls express` |
| `npm explain <package>` | Explain why package is installed | `npm explain express` |
| `npm fund` | Show funding information | `npm fund` |
| `npm doctor` | Check npm environment | `npm doctor` |

### Registry Operations
| Command | Description | Example |
|---------|-------------|---------|
| `npm star <package>` | Star a package | `npm star express` |
| `npm unstar <package>` | Unstar a package | `npm unstar express` |
| `npm stars` | List starred packages | `npm stars` |
| `npm deprecate <package>@<version> <message>` | Deprecate package version | `npm deprecate my-package@1.0.0 "Use 2.0.0"` |

### Package.json Fields
```json
{
  "name": "my-package",
  "version": "1.0.0",
  "description": "A sample package",
  "main": "index.js",
  "scripts": {
    "start": "node index.js",
    "test": "jest"
  },
  "keywords": ["node", "npm"],
  "author": "John Doe <john@example.com>",
  "license": "MIT",
  "dependencies": {
    "express": "^4.18.0"
  },
  "devDependencies": {
    "jest": "^27.0.0"
  },
  "peerDependencies": {
    "react": ">=16.0.0"
  },
  "engines": {
    "node": ">=14.0.0",
    "npm": ">=6.0.0"
  },
  "files": [
    "lib/",
    "index.js",
    "README.md"
  ],
  "repository": {
    "type": "git",
    "url": "https://github.com/user/repo.git"
  },
  "bugs": {
    "url": "https://github.com/user/repo/issues"
  },
  "homepage": "https://github.com/user/repo#readme"
}
```

---

## Resources
- [npm Documentation](https://docs.npmjs.com/)
- [npm Registry](https://www.npmjs.com/)
- [package.json Reference](https://docs.npmjs.com/cli/v7/configuring-npm/package-json)
- [Semantic Versioning](https://semver.org/)
- [npm CLI Commands](https://docs.npmjs.com/cli/v7/commands)

---
*Originally compiled from various sources. Contributions welcome!*
