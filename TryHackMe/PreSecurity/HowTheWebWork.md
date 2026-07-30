# Module 6 - DNS, HTTP & Websites

## 1. DNS (Domain Name System)

### What is DNS?
DNS translates a domain name into an IP address.

**Example:**
- `google.com` → `142.250.x.x`

### DNS Record Types
- **A** – Maps domain to IPv4 address
- **AAAA** – Maps domain to IPv6 address
- **CNAME** – Alias for another domain
- **MX** – Mail server
- **TXT** – Stores text information
- **NS** – Name server

### DNS Process
1. User enters a domain name.
2. DNS server finds the corresponding IP address.
3. Browser connects to the web server.

---

## 2. HTTP (HyperText Transfer Protocol)

### What is HTTP?
A protocol used to transfer web pages between a browser and a web server.

### HTTP Methods
- `GET` – Retrieve data
- `POST` – Send data
- `PUT` – Update data
- `DELETE` – Delete data

### Common Status Codes
- **200** – OK
- **301** – Moved Permanently
- **403** – Forbidden
- **404** – Not Found
- **500** – Internal Server Error

### HTTP vs HTTPS

| HTTP | HTTPS |
|------|-------|
| Not Secure | Secure |
| Port 80 | Port 443 |
| No Encryption | Uses SSL/TLS Encryption |

---

## 3. How Websites Work

### Main Components
- Client (Browser)
- DNS
- Web Server
- Database

### Website Loading Process
1. User enters URL.
2. DNS resolves the domain to an IP address.
3. Browser sends an HTTP/HTTPS request.
4. Web server processes the request.
5. Server returns the web page.
6. Browser displays the page.

### Frontend
- HTML
- CSS
- JavaScript

### Backend
- PHP
- Python
- Java
- Node.js

---

## 4. Putting It All Together

### Website Request Flow

```
User
  ↓
Browser
  ↓
DNS Server
  ↓
Web Server
  ↓
Database
  ↓
Response
  ↓
Browser Displays Website
```

### Key Terms
- URL
- Domain Name
- IP Address
- DNS
- HTTP
- HTTPS
- Web Server
- Browser
- HTML
- CSS
- JavaScript

---

## Key Takeaways

- DNS converts domain names into IP addresses.
- HTTP transfers web data; HTTPS adds encryption.
- Websites use frontend and backend technologies.
- A browser communicates with servers using HTTP/HTTPS after DNS resolution.