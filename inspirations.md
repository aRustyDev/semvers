Top Recommendations

### 1. **GitVersion** ⭐
- Language-agnostic tool that analyzes git history
- Reads tags and branch patterns to determine versions
- Can read from various manifest files
- Works with multiple branching strategies (GitFlow, GitHub Flow, etc.)

### 2. **release-please** (Google)
- Analyzes conventional commits to determine version bumps
- Generates and maintains CHANGELOG.md
- Can read/update version in package.json, pyproject.toml, Cargo.toml, etc.
- Multi-language support (Node.js, Python, Rust, Go, Java, etc.)

### 3. **commit-and-tag-version** (fork of standard-version)
- Analyzes conventional commits for version bumping
- Generates CHANGELOG from git history
- Updates version in package.json, lock files
- CLI-friendly

### 4. **python-semantic-release (PSR)**
For Python projects:
- Parses commit messages to determine version bumps
- Updates version in pyproject.toml, setup.py, etc.
- Generates changelogs
- CI/CD integration support

### 5. **Commitizen**
Multi-language support:
```bash
cz bump  # Analyzes commits and bumps version
```
- Reads/writes versions to various manifest files
- Generates changelogs
- Python, Node.js support

## Specialized Tools

### **semver-action** (GitHub Action)
```yaml
- uses: ietf-tools/semver-action@v1
  with:
    token: ${{ secrets.GITHUB_TOKEN }}
```
- Analyzes conventional commits between tags
- Returns the calculated next version
- Monorepo support

### **Cocogitto** (Rust-based)
```bash
cog bump --auto  # Calculates version from commits
```
- Fast CLI tool
- Conventional commits parser
- Generates changelogs
- Works with any language

### **bump-my-version** (Python)
```bash
bump-my-version bump --parse-current-version
```
- Actively maintained (2025)
- Reads version from config files
- Supports custom version schemes
- Can parse lock files via config

## For Your Specific Requirements

**Reading from lock files/manifests:**
- **release-please**: Best for reading/updating versions in multiple file types
- **GitVersion**: Can extract versions from AssemblyInfo, package.json, etc.
- **bump-my-version**: Highly configurable for custom file parsing

**Changelog/diff analysis:**
- **release-please**: Excellent at parsing conventional commits
- **Cocogitto**: Fast commit analyzer with changelog generation
- **semver-action**: Good for CI/CD pipelines

**Example with release-please:**
```bash
# Analyzes commits since last release
release-please release-pr \
  --repo-url=owner/repo \
  --token=$GITHUB_TOKEN

# Reads version from package.json and bumps appropriately
```

**Example with GitVersion:**
```bash
# Reads git history and determines next version
gitversion /showvariable SemVer

# Can also read from gitversion.yml config
```

Would you like me to help you set up any of these tools for your specific use case?
