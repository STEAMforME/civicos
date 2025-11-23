# Security Policy

## Supported Versions

We release patches for security vulnerabilities for the following versions:

| Version | Supported          |
| ------- | ------------------ |
| 1.x     | :white_check_mark: |
| < 1.0   | :x:                |

## Reporting a Vulnerability

### Please DO NOT report security vulnerabilities through public GitHub issues.

Instead, please report them via email to:

**security@steamforme.org**

### What to Include

Please include:

1. **Description** - Detailed description of the vulnerability
2. **Impact** - What an attacker could do with this vulnerability
3. **Steps to Reproduce** - Clear steps to reproduce the issue
4. **Proof of Concept** - Code or screenshots demonstrating the issue
5. **Suggested Fix** - If you have ideas (optional)

### What to Expect

- **Acknowledgment** - We'll acknowledge receipt within 48 hours
- **Initial Response** - We'll provide an initial assessment within 5 business days
- **Updates** - We'll keep you updated on our progress
- **Resolution** - We aim to resolve critical issues within 30 days
- **Credit** - We'll credit you in our security advisories (if desired)

### Disclosure Policy

We follow coordinated disclosure:

1. We'll work with you to understand and validate the issue
2. We'll develop and test a fix
3. We'll release the fix in a security update
4. We'll publicly disclose the vulnerability after the fix is released

## Security Best Practices

### For Users

- Keep CivicOS updated to the latest version
- Use HTTPS for all deployments
- Implement Content Security Policy headers
- Regularly review access controls
- Enable security monitoring and logging

### For Developers

- Never commit sensitive data (API keys, passwords)
- Validate and sanitize all user input
- Use parameterized queries (when backend is added)
- Implement rate limiting
- Follow OWASP security guidelines

## Known Security Considerations

### Current Version (v1.0)

The MVP is a static site with minimal security concerns:

- **No server-side code** - Reduces attack surface
- **No database** - No SQL injection risk
- **No user authentication** - No credential theft risk
- **Client-side only** - Standard web security applies

### Future Versions

As we add backend features, we'll implement:

- [ ] Authentication and authorization
- [ ] Input validation and sanitization
- [ ] Rate limiting
- [ ] CSRF protection
- [ ] SQL injection prevention
- [ ] XSS protection
- [ ] Security headers
- [ ] Regular security audits

## Security Updates

We'll announce security updates via:

- GitHub Security Advisories
- Repository releases
- Email to registered users (future)

## Bug Bounty Program

We don't currently have a bug bounty program, but we deeply appreciate security researchers who help keep CivicOS safe. We'll:

- Acknowledge your contribution publicly (if desired)
- Prioritize fixing reported vulnerabilities
- Keep you updated on our progress

## Questions?

For security questions that aren't vulnerabilities, email hello@steamforme.org

---

**Thank you for helping keep CivicOS and our communities safe!**