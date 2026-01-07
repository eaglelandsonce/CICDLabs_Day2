# Security Policy

## Reporting Security Issues

If you discover a security vulnerability in this project, please report it by emailing security@example.com.

**Do not open a public issue.**

## Security Best Practices

### 1. Secrets Management
- Never commit secrets to Git
- Use GitHub Secrets for sensitive values
- Rotate credentials regularly
- Use `.env.example` for documentation, `.env` for actual secrets (gitignored)

### 2. Dependency Management
- Run `safety check` before every release
- Monitor for known vulnerabilities
- Update dependencies promptly
- Use pinned versions in production

### 3. Code Security
- Run Bandit for Python security issues
- Use Semgrep for pattern-based security scanning
- Conduct code reviews focusing on security
- Never hardcode credentials

### 4. Deployment Security
- Require manual approval for production
- Use least-privilege service accounts
- Enable audit logging
- Implement rate limiting

### 5. CI/CD Security
- Scan Docker images for vulnerabilities
- Use signed commits
- Implement SBOM (Software Bill of Materials)
- Run security tests in every pipeline

## Automated Security Checks

This project uses:
- **Bandit**: Python security linter
- **Safety**: Dependency vulnerability scanner
- **Semgrep**: Static analysis tool
- **GitHub Secret Scanning**: Detects hardcoded secrets

## Security Workflow

1. Developer pushes code
2. CI runs security scans (Bandit, Safety)
3. If vulnerabilities found, build fails
4. Security team reviews weekly scan results
5. Production deploys require manual approval
