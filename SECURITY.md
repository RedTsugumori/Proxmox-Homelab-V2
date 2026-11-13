# Public repository security policy

This repository is public. Sanitize all materials before committing.

Never publish personally identifiable information, passwords, tokens, private keys, recovery codes, serial numbers, MAC addresses, real public IP addresses, identifying hostnames, management endpoints, or sensitive network topology. Review screenshots, logs, configuration exports, and metadata. Use documentation placeholders such as `192.0.2.10`, `admin@example.com`, and `node-01`.

A `.gitignore` is not a security boundary. Removing secrets in later commits does not erase Git history. Revoke accidentally exposed credentials immediately.
