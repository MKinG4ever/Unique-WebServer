# NexusFeature Web Interface (WI)

Version: 2.0  
Domain: https://nexusfeature.ddnsfree.com

---

## 📌 Overview

NexusFeature Web Interface (WI) is a lightweight web application framework designed to host modular web services through
a clean frontend and versioned API system.

It is powered by:

- Nginx (HTTP/2 + TLS 1.2/1.3)
- Python backend (app/main.py)
- Static asset serving with aggressive caching
- Versioned API routing (/api/v1, /api/v2)

---

## 📂 Project Structure

```
nexusfeature.ddnsfree.com/
├─ api/
│ ├─ v1/
│ │ └─ update
│ └─ v2/
│   └─ update
│
├─ app/
│ ├─ init.py
│ └─ main.py
│
├─ configs/
│ ├─ 10K.txt
│ ├─ dns
│ └─ users
│
├─ static/
│ ├─ css/
│ │ └─ style.css
│ ├─ js/
│ │ └─ script.js
│ └─ images/
│ └─ favicon.ico
│
├─ templates/
│ ├─ errors/
│ │ ├─ 403.html
│ │ ├─ 404.html
│ │ └─ 500.html
│ ├─ DNSTest.html
│ ├─ SiteViewer.html
│ └─ UserCheck.html
│
├─ index.html
├─ sitemap.xml
└─ README.md
```

---

## 🚀 Features

- Dual-stack IPv4 / IPv6 support
- HTTPS enforced with automatic redirect
- HTTP/2 enabled
- Secure headers configured
- Gzip compression
- Static file caching (30 days)
- API versioning support
- Custom error pages
- Sensitive directory protection

---

## 🔐 Security

The server configuration includes:

- TLS 1.2 / TLS 1.3 only
- Strong cipher suite
- Server token hiding
- Access restrictions to:
    - `/configs`
    - `/app`
    - hidden dot-files
- Custom error pages
- Optional HSTS support

---

## 🌐 API

Current API endpoints:

- `/api/v1/update`
- `/api/v2/update`

Currently returning HTTP 503 until backend proxy is enabled.

To enable backend proxy:
Uncomment proxy_pass settings inside nginx.conf.

---

## 🛠 Deployment

### Restart Nginx

```bash
sudo systemctl restart nginx
