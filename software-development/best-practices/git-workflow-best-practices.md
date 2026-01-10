# Git Workflow Best Practices

## Summary

Git workflow best practices are essential for maintaining code quality, enabling collaboration, and ensuring project stability in software development teams. This guide covers proven Git workflows, branching strategies, commit message conventions, and collaboration patterns. You'll learn how to structure your Git repository for effective team collaboration, implement code review processes, and maintain a clean project history.

## Prerequisites

- Basic understanding of Git commands (clone, add, commit, push, pull)
- Familiarity with version control concepts
- Command-line experience or Git GUI tool knowledge
- Understanding of software development lifecycle

## Content

### Why Git Workflow Matters

Effective Git workflows enable teams to:
- **Collaborate smoothly** without code conflicts
- **Maintain code quality** through structured review processes
- **Track changes** with clear, meaningful commit history
- **Deploy confidently** with tested, stable releases
- **Enable parallel development** on multiple features simultaneously

### Common Git Workflow Models

#### 1. Git Flow

Git Flow is a branching model designed around project releases. It defines strict branch roles and merges.

**Branch Structure:**
- **main/master**: Production-ready code
- **develop**: Integration branch for features
- **feature/***: New features
- **release/***: Preparation for releases
- **hotfix/***: Critical production fixes

**When to Use:**
- Projects with scheduled releases
- Large teams with multiple features in development
- Need for version tracking

#### 2. GitHub Flow

Simplified workflow with main branch and feature branches. Continuous deployment model.

**Branch Structure:**
- **main**: Always deployable
- **feature/***: Feature branches merged to main

**Workflow:**
1. Create feature branch from main
2. Make changes and commit
3. Open Pull Request
4. Review and merge to main
5. Deploy immediately

**When to Use:**
- Continuous deployment environments
- Smaller teams
- Web applications and services

#### 3. GitLab Flow

Combines Git Flow with environment branches. Uses upstream-first principle.

**Branch Structure:**
- **main**: Development branch
- **production**: Production code
- **pre-production**: Staging environment
- **feature/***: Feature branches

**When to Use:**
- Need for environment-specific deployments
- Complex deployment pipelines

#### 4. Trunk-Based Development

Minimal branching. Most work happens directly on main with short-lived feature branches.

**Branch Structure:**
- **main**: Primary branch
- **feature/***: Very short-lived branches (hours/days)

**When to Use:**
- Extreme programming environments
- Very small teams
- Continuous integration focus

### Branching Strategies

#### Feature Branch Strategy

Create isolated branches for each feature or task.

**Naming Conventions:**
```
feature/user-authentication
feature/add-payment-gateway
bugfix/login-error-handling
hotfix/security-patch
refactor/api-structure
```

**Best Practices:**
- Keep branches small and focused
- Keep branches short-lived (merge within days/weeks)
- Name branches descriptively
- Delete branches after merging

#### Branch Protection Rules

Protect critical branches from direct pushes:

```yaml
# GitHub/GitLab Branch Protection Example
main:
  required_reviews: 2
  require_status_checks: true
  required_status_checks:
    - ci/tests
    - ci/lint
  enforce_admins: true
  required_linear_history: true
```

**Benefits:**
- Prevents force pushes to main
- Requires code reviews
- Ensures tests pass before merge
- Maintains linear history

### Commit Message Best Practices

#### Commit Message Format

Follow the Conventional Commits specification:

```
<type>(<scope>): <subject>

<body>

<footer>
```

#### Commit Types

- **feat**: New feature
- **fix**: Bug fix
- **docs**: Documentation changes
- **style**: Formatting, missing semicolons, etc.
- **refactor**: Code restructuring
- **test**: Adding or updating tests
- **chore**: Maintenance tasks, dependency updates

#### Examples

**Good Commit Messages:**
```
feat(auth): Add JWT token authentication

Implement JWT-based authentication system with token refresh.
Add middleware for protected routes.

Closes #123

fix(api): Resolve null pointer exception in user endpoint

The /users/:id endpoint was throwing NPE when user not found.
Added proper null check and error handling.

Fixes #456

docs(readme): Update installation instructions

Add Windows-specific installation steps and prerequisites.
```

**Bad Commit Messages:**
```
❌ "fix bug"
❌ "update"
❌ "changes"
❌ "WIP"
❌ "asdf"
```

### Collaboration Workflows

#### Pull Request Process

1. **Create Feature Branch**
   ```bash
   git checkout -b feature/new-feature
   ```

2. **Make Changes and Commit**
   ```bash
   git add .
   git commit -m "feat: implement feature X"
   ```

3. **Push to Remote**
   ```bash
   git push origin feature/new-feature
   ```

4. **Open Pull Request**
   - Include clear description
   - Reference related issues
   - Request specific reviewers
   - Add labels (feature, bug, etc.)

5. **Address Review Comments**
   ```bash
   git add .
   git commit -m "fix: address review feedback"
   git push origin feature/new-feature
   ```

6. **Merge After Approval**
   - Squash commits if needed
   - Delete branch after merge
   - Update related issues

#### Code Review Best Practices

**For Authors:**
- Keep PRs small and focused
- Write clear PR descriptions
- Respond to feedback promptly
- Test changes thoroughly before review

**For Reviewers:**
- Review within 24-48 hours
- Be constructive and respectful
- Focus on code quality, not style preferences
- Approve or request changes clearly

### Git Repository Organization

#### .gitignore Best Practices

Maintain comprehensive `.gitignore` files:

```gitignore
# Dependencies
node_modules/
vendor/
__pycache__/

# Build outputs
dist/
build/
*.o
*.class

# Environment variables
.env
.env.local
.env.*.local

# IDE files
.vscode/
.idea/
*.swp
*.swo
*~

# OS files
.DS_Store
Thumbs.db

# Logs
*.log
logs/

# Temporary files
*.tmp
*.temp
```

#### Repository Structure

Organize repository logically:

```
project-root/
├── src/              # Source code
├── tests/            # Test files
├── docs/             # Documentation
├── .github/          # GitHub workflows
├── scripts/          # Utility scripts
├── .gitignore
├── README.md
└── LICENSE
```

## Examples

### Example 1: Feature Development Workflow

Complete workflow from feature start to merge:

```bash
# 1. Update main branch
git checkout main
git pull origin main

# 2. Create feature branch
git checkout -b feature/user-profile

# 3. Make changes
# ... edit files ...

# 4. Stage changes
git add src/components/UserProfile.jsx
git add src/styles/profile.css

# 5. Commit with proper message
git commit -m "feat(profile): Add user profile component

- Create UserProfile component with avatar and bio
- Add responsive styling for mobile devices
- Include profile edit functionality

Closes #234"

# 6. Push to remote
git push origin feature/user-profile

# 7. After PR approval, merge (done via GitHub UI typically)
# Then cleanup:
git checkout main
git pull origin main
git branch -d feature/user-profile  # Delete local branch
```

**Explanation:**
This workflow demonstrates a complete feature development cycle, from branch creation to cleanup. Each step follows best practices with descriptive naming and proper commit messages.

### Example 2: Handling Merge Conflicts

```bash
# Attempting to merge feature branch
git checkout main
git pull origin main
git merge feature/new-feature

# Conflict detected:
# CONFLICT (content): Merge conflict in src/utils/helpers.js

# Open conflicted file and resolve:
# <<<<<<< HEAD
# function processData(data) {
#     return data.map(x => x * 2);
# }
# =======
# function processData(data) {
#     return data.map(x => x * 3);
# }
# >>>>>>> feature/new-feature

# After resolving manually:
git add src/utils/helpers.js
git commit -m "merge: resolve conflict in helpers.js"
```

**Explanation:**
When conflicts occur, Git marks the conflicting sections. Manually resolve by choosing the correct code or combining changes, then stage and commit the resolution.

### Example 3: Interactive Rebase for Clean History

Cleaning up commit history before PR:

```bash
# Start interactive rebase (last 3 commits)
git rebase -i HEAD~3

# Editor opens with:
# pick abc123 feat: add login form
# pick def456 fix: correct validation
# pick ghi789 docs: update readme

# Change to:
# pick abc123 feat: add login form
# squash def456 fix: correct validation
# squash ghi789 docs: update readme

# Save and close, then edit commit message
# Final result: Single clean commit
```

**Explanation:**
Interactive rebase allows combining multiple commits into one clean commit before sharing with others. This creates a more readable project history.

## Troubleshooting

### Issue: Accidentally Committed Sensitive Data

**Symptoms:**
- API keys, passwords, or tokens visible in commit history
- Security concerns about exposed credentials

**Solution:**
```bash
# 1. Remove file from Git history (if not pushed)
git rm --cached .env
git commit --amend

# 2. If already pushed, use git filter-repo or BFG Repo-Cleaner
# 3. Rotate all exposed credentials immediately
# 4. Add file to .gitignore
# 5. Force push (coordinate with team)
```

**Prevention:**
- Always check `.gitignore` before committing
- Use environment variables
- Use Git hooks to scan for secrets

### Issue: Lost Uncommitted Changes

**Symptoms:**
- Local changes disappeared after checkout or reset
- Cannot find work-in-progress code

**Solution:**
```bash
# Check reflog for recent commits
git reflog

# Recover from stash if stashed
git stash list
git stash apply stash@{0}

# Check for uncommitted changes in working directory
git fsck --lost-found
```

**Prevention:**
- Commit frequently
- Use stash for temporary saves
- Push to remote regularly

### Issue: Merge Conflicts in Large Files

**Symptoms:**
- Binary file conflicts
- Large JSON/XML files with many conflicts
- Difficult to resolve conflicts manually

**Solution:**
1. Decide which version to keep
2. Use `git checkout --ours <file>` or `git checkout --theirs <file>`
3. If combining needed, use specialized merge tools
4. For binary files, usually choose one version entirely

## Best Practices

### 1. Commit Frequently with Clear Messages

- Commit small, logical changesets
- Write descriptive commit messages
- Follow commit message conventions
- Review commits before pushing

### 2. Keep Branches Focused and Short-Lived

- One feature per branch
- Merge within days/weeks, not months
- Delete branches after merging
- Avoid long-running feature branches

### 3. Use Pull Requests for Code Review

- Never push directly to main
- Require reviews for critical branches
- Use PR templates for consistency
- Keep PRs small and reviewable

### 4. Maintain Clean Project History

- Use interactive rebase for cleanup (before sharing)
- Avoid "WIP" commits in main branch
- Squash commits when appropriate
- Write meaningful commit messages

### 5. Protect Critical Branches

- Enable branch protection rules
- Require status checks to pass
- Enforce code review requirements
- Prevent force pushes to main

### 6. Handle Sensitive Data Carefully

- Never commit passwords, keys, or tokens
- Use environment variables
- Maintain comprehensive `.gitignore`
- Scan commits for secrets automatically

## Conclusion

Effective Git workflows are essential for successful software development projects. By following proven branching strategies, writing clear commit messages, and maintaining proper collaboration processes, teams can work efficiently while maintaining code quality.

**Key Takeaways:**
- Choose workflow model based on team size and deployment frequency
- Use feature branches for isolation and collaboration
- Write descriptive, conventional commit messages
- Implement code review processes
- Protect critical branches and maintain clean history

**Next Steps:**
- Evaluate your current Git workflow
- Establish team conventions and document them
- Set up branch protection rules
- Implement automated checks and CI/CD integration
- Train team on workflow best practices

**Related Topics to Explore:**
- Continuous Integration/Continuous Deployment (CI/CD)
- Automated Testing Strategies
- Code Review Tools and Processes
- Git Hooks and Automation
- Repository Security Practices

## References

- [Conventional Commits Specification](https://www.conventionalcommits.org/) - Commit message conventions
- [Git Flow Documentation](https://nvie.com/posts/a-successful-git-branching-model/) - Original Git Flow model
- [GitHub Flow Guide](https://guides.github.com/introduction/flow/) - GitHub's workflow model
- [Pro Git Book](https://git-scm.com/book) - Comprehensive Git reference
- [GitHub Branch Protection](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-protected-branches) - Branch protection documentation

## Related Articles

- [CI/CD Pipeline Setup](../devops/cicd-pipeline-setup.md) - _Coming soon_
- [Code Review Best Practices](../best-practices/code-review-guide.md) - _Coming soon_
- [Version Control Security](../security/version-control-security.md) - _Coming soon_

---

**Last Updated:** January 2024

**Author:** FS Wiki Community

