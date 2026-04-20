# 🖥️ Server Environment Practice

Documentation and hands-on practice for configuring server environments across **CentOS** and **Debian** distributions — covering essential services used in ITNSA competition.

---

## 📋 Topics Covered

| Service | CentOS | Debian |
|---|:---:|:---:|
| DNS Server | ✅ | ✅ |
| Web Server | ✅ | ✅ |
| Web Mail | ✅ | ✅ |
| FTP Server | ✅ | ✅ |
| SSH | ✅ | ✅ |
| Certificate Authority (CA) | ❌ | ✅ |

---

## 🌐 DNS Server

Domain Name System — resolving domain names to IP addresses.

**Packages:**
- CentOS: `bind`, `bind-utils`
- Debian: `bind9`, `bind9utils`

**Key Concepts:**
- Forward & Reverse Zone configuration
- A, CNAME, MX, NS, PTR records
- Named configuration (`/etc/named.conf` / `/etc/bind/named.conf`)

**Practice Files:**
```
dns/
├── centos/
│   ├── named.conf
│   └── zone-files/
└── debian/
    ├── named.conf.local
    └── zone-files/
```

---

## 🌍 Web Server

Serving web content via HTTP/HTTPS.

**Packages:**
- CentOS: `httpd` (Apache)
- Debian: `apache2`

**Key Concepts:**
- Virtual Host configuration
- HTTP to HTTPS redirect
- SSL/TLS certificate setup (self-signed)
- Directory permissions & `.htaccess`

**Practice Files:**
```
web-server/
├── centos/
│   ├── httpd.conf
│   └── vhosts/
└── debian/
    ├── apache2.conf
    └── sites-available/
```

---

## 📬 Web Mail

Browser-based email client integrated with a mail server.

**Packages:**
- Mail Server: `postfix` (SMTP), `dovecot` (IMAP/POP3)
- Web Mail Client: `Roundcube`

**Key Concepts:**
- Postfix SMTP configuration
- Dovecot IMAP/POP3 setup
- Roundcube installation & integration
- Mail domain and user management

**Practice Files:**
```
webmail/
├── centos/
│   ├── postfix/
│   ├── dovecot/
│   └── roundcube/
└── debian/
    ├── postfix/
    ├── dovecot/
    └── roundcube/
```

---

## 📂 FTP Server

File Transfer Protocol — transferring files between client and server.

**Packages:**
- CentOS & Debian: `vsftpd`

**Key Concepts:**
- Active vs Passive mode
- Anonymous vs Authenticated access
- Chroot jail for user isolation
- FTP over TLS (FTPS)

**Practice Files:**
```
ftp/
├── centos/
│   └── vsftpd.conf
└── debian/
    └── vsftpd.conf
```

---

## 🔐 SSH

Secure Shell — remote server access and management.

**Packages:**
- CentOS & Debian: `openssh-server`

**Key Concepts:**
- SSH key-based authentication (passwordless login)
- `sshd_config` hardening (disable root login, change port, etc.)
- SSH tunneling basics
- Managing authorized keys

**Practice Files:**
```
ssh/
├── centos/
│   └── sshd_config
└── debian/
    └── sshd_config
```

---

## 🔏 Certificate Authority (CA)

Creating an internal CA to sign SSL/TLS certificates for services — Debian only.

**Packages:**
- Debian: `openssl`

**Key Concepts:**
- Generating a Root CA (private key + self-signed certificate)
- Signing server certificates with the Root CA
- Installing the Root CA to be trusted by clients
- Applying signed certificates to Apache (HTTPS), Dovecot, Postfix, vsftpd

**Workflow:**
```
[Root CA] → signs → [Server Certificate] → applied to → [Service (Apache, Postfix, Dovecot, vsftpd)]
```

**Practice Files:**
```
ca/
└── debian/
    ├── create-root-ca.sh
    ├── create-server-cert.sh
    └── certs/
        ├── rootCA.key
        ├── rootCA.crt
        ├── server.key
        ├── server.csr
        └── server.crt
```

---

## 🗂️ Full Directory Structure

```
Server-Environment-Practice/
├── dns/
│   ├── centos/
│   └── debian/
├── web-server/
│   ├── centos/
│   └── debian/
├── webmail/
│   ├── centos/
│   └── debian/
├── ftp/
│   ├── centos/
│   └── debian/
├── ssh/
│   ├── centos/
│   └── debian/
├── ca/
│   └── debian/
└── README.md
```

---

## 🛠️ Environment

![CentOS](https://img.shields.io/badge/CentOS-262577?style=flat&logo=centos&logoColor=white)
![Debian](https://img.shields.io/badge/Debian-A81D33?style=flat&logo=debian&logoColor=white)
![Apache](https://img.shields.io/badge/Apache-D22128?style=flat&logo=apache&logoColor=white)
![Postfix](https://img.shields.io/badge/Postfix-SMTP-orange?style=flat)
![vsftpd](https://img.shields.io/badge/vsftpd-FTP-blue?style=flat)
![OpenSSH](https://img.shields.io/badge/OpenSSH-black?style=flat&logo=openssh&logoColor=white)

---

## 📌 Quick Reference — Service Management

```bash
# CentOS (systemctl)
systemctl start <service>
systemctl enable <service>
systemctl status <service>

# Debian (systemctl)
systemctl start <service>
systemctl enable <service>
systemctl status <service>
```

Common service names:

| Service | CentOS | Debian |
|---|---|---|
| DNS | `named` | `bind9` |
| Web Server | `httpd` | `apache2` |
| FTP | `vsftpd` | `vsftpd` |
| SSH | `sshd` | `ssh` |
| Mail (SMTP) | `postfix` | `postfix` |
| Mail (IMAP) | `dovecot` | `dovecot` |

---

> *"Know your services, know your system."*
