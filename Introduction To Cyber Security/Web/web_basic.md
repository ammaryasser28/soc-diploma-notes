# Web Basics – Complete Guide

---

## 1️⃣ Website Creation

- To create a website for a specific purpose, the first step is **writing the necessary code**.
- The code is divided into:
  - **Front-End**: The part the user interacts with (HTML, CSS, JavaScript)
  - **Back-End**: The part that handles application logic, database operations, and server processing
- All code is stored in **files** on the server.
- Additional resources include:
  - Images
  - Videos
  - Libraries or modules

---

## 2️⃣ Static vs Dynamic Websites

- **Static Website**:
  - Server returns the file as-is
  - No back-end processing
  - Example: simple informational page

- **Dynamic Website**:
  - Server executes back-end code (PHP, Python, Node.js)
  - Interacts with databases to generate HTML on-the-fly
  - Example: social media or e-commerce websites

---

## 3️⃣ Homepage

- Every website should have a **Homepage**, usually named:
`index.html`
- This is the first page loaded when a user enters the website URL.

---

## 4️⃣ Making the Website Accessible Online

- To make a website discoverable on the Internet, you need a **domain name**.
- The domain maps to your server, making it reachable globally.
- Options:
- Use a dedicated web server
- Configure your personal computer as a web server

---

## 5️⃣ Web Server Setup

- Install a web server software such as:
- **Apache**
- **Nginx**
- Specify the **root directory** where all website files will reside.
- Place the homepage (`index.html`) inside this directory.

---

## 6️⃣ Web Server vs Application Server

- **Web Server**:
- Handles HTTP requests
- Serves static files
- Forwards complex requests to the application server

- **Application Server**:
- Executes application logic
- Interacts with databases
- Can cause **500 errors** if something fails internally

---

## 7️⃣ Ports

- Web servers listen on:
- **Port 80** → HTTP
- **Port 443** → HTTPS
- These ports handle incoming client requests.

---

## 8️⃣ HTTP and HTTPS

- Clients access websites using **HTTP** or **HTTPS**.
- **HTTPS** uses **TLS encryption** to secure communication.
- Certificates verify the server’s authenticity.
- Ensures protection against **Man-in-the-Middle attacks**.

---

## 9️⃣ HTTP Requests

- The browser acts as a **client**.
- It sends requests like:
`GET /index.html`
- Clients **request**, servers **respond** with data and status codes.

---

## 🔟 HTTP Responses and Status Codes

- The server responds with:
- Requested file
- **HTTP status code**
- Optional headers (e.g., `Content-Type`)

### ✅ 200 Series – Success
- **200 OK** → Request successful, file delivered

### 🔁 300 Series – Redirection
- **301** → Moved permanently
- **302** → Moved temporarily

### ❌ 400 Series – Client Errors
- **404 Not Found** → File does not exist
- **403 Forbidden** → File exists but client lacks permission
- Repeated 403 or 404 from same IP may indicate **malicious activity**

### 🔥 500 Series – Server Errors
- Internal server problems or back-end code failures

<img width="740" height="289" alt="image" src="https://github.com/user-attachments/assets/5e525aa9-f222-4576-8db7-40855da8faa0" />

---

## 1️⃣1️⃣ Loading Additional Resources

- Browser parses `index.html`.
- Finds references to:
- Images
- Videos
- Scripts
- Sends additional requests:
`GET logo.png`

---

## 1️⃣2️⃣ Content-Type Header

- Server specifies file type:
`Content-Type: text/html
Content-Type: image/png`
- Helps the browser render files correctly.

---

## 1️⃣3️⃣ CDN (Content Delivery Network)

- Some resources may be hosted externally on **CDNs**.
- Example in HTML:
```html
<img src="https://cdn.example.com/logo.png">
```
- Browser sends separate requests to retrieve these resources.

## 1️⃣4️⃣ Redirection for Resources

If a file moves, the server responds with:

- **301** → Permanent redirect
- **302** → Temporary redirect

The browser automatically follows the new URL.

<img width="738" height="288" alt="image" src="https://github.com/user-attachments/assets/4d14bbf7-ec0f-411e-b5f7-a9254cc0d608" />

---

## 1️⃣5️⃣ Caching & Parallel Requests

Browsers may **cache resources** to reduce loading times:

- Images
- CSS
- Scripts

Browsers load multiple resources **in parallel**, improving performance.

---

## ✅ Summary

- Browsers request, servers respond.
- Status codes indicate the outcome of requests.
- Resources may be loaded from multiple servers including CDNs.
- HTTPS secures communication.
- Logs, status codes, and 403/404 monitoring are important for security.
- Caching and parallel requests improve website speed and efficiency.



