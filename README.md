# Mega-Hacking-Project---Amir-Shaikh

**Project: OWASP Juice Shop Pentesting Lab**

**Course:** COMP‑357: Advanced Pentesting

**Exercise:** - JWT Exploitation & Mitigation

**Student:** Amirhusen S Shaikh

**Overview**

This repository contains all artifacts and documentation for the pentesting lab conducted against the OWASP Juice Shop application. The lab demonstrates a **JWT privilege escalation exploit** and provides mitigation strategies to secure the application.

**Deliverables included**:

- Lab Creation Guide
- Attack Report
- Purple Team Mitigation Report
- Infrastructure artifacts (docker-compose.yml, VM specs)
- Evidence screenshots

**Lab Setup**

**Prerequisites**

- Kali Linux VM (VirtualBox)
- Docker **(27.5.1)**
- Python3 + venv
- jwt_tool

**Deployment**

- Clone this repository.
- Ensure Docker is installed and running.
- Start Juice Shop using Docker Compose:
  - Command: **docker-compose up -d**
- Access the application in your browser:
  - <http://localhost:3000>

**Credentials & Secrets**

- Test accounts created in Juice Shop (redacted in reports).
- JWT secret discovered as secret (documented for exploit, redacted in final submission).
- Secrets are provisioned via Docker runtime and stored securely.

**Exploit Summary**

- **Vulnerability**: JWT algorithm confusion + weak secret.
- **Attack Goal**: Escalate from customer to admin.
- **Method**: Forge **HS256** token with secret key.
- **Evidence**: Screenshots of decoded token, forged token, DevTools replacement, and solved challenge banner.

**Mitigation Summary**

- Enforce **RS256** only.
- Use **strong, rotated secrets** stored securely.
- Validate roles server‑side.
- Place Juice Shop behind a reverse proxy for **JWT validation**.
- **Harden Docker** containers and **monitor logs**.

**Version**

- Initial release: **v1.0**
