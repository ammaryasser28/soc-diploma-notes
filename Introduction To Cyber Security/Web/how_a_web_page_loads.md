# Web Exercise – How a Web Page Loads

## Scenario

A user types `website.com` in a browser.  
The page contains:
- A **logo image** hosted on `resources.com`
- A **video** hosted on `videos.com`

---

## 1️⃣ User Types URL & Browser Check

1. User types the website URL:
`website.com`
2. Browser checks **local DNS cache**.
3. If not found, queries the OS cache.
4. If still not found, queries the **DNS resolver (ISP)**.

---

## 2️⃣ DNS Resolution

1. DNS resolver queries:
   - Root DNS → `.com` TLD → Authoritative DNS for `website.com`
2. Authoritative DNS returns the **IP address**.
3. Browser caches the IP for future requests.

> **Ports involved:** DNS uses **UDP/53** or **TCP/53**.

---

## 3️⃣ TCP Connection & TLS Handshake

1. Browser initiates **TCP three-way handshake** with server IP:
   - SYN → SYN-ACK → ACK
2. Default ports:
   - **Port 80** → HTTP
   - **Port 443** → HTTPS
3. If HTTPS:
   - **TLS handshake** secures communication
   - Certificates verified

---

## 4️⃣ HTTP Request for Homepage

Browser sends:
`
GET / HTTP/1.1
Host: website.com
`
- Over TCP/Port 80 (HTTP) or TCP/Port 443 (HTTPS)

---

## 5️⃣ Server Response

- HTML content
- **Status Code 200 OK**
- Headers like `Content-Type` and `Cache-Control`
- Browser starts parsing HTML **immediately**.

---

## 6️⃣ Parsing HTML & Discovering External Resources

Browser finds:
- `<img src="https://resources.com/logo.png">`
- `<video src="https://videos.com/video.mp4">`

> Each requires separate DNS resolution, TCP/TLS connection, and GET request.

---

## 7️⃣ DNS & HTTP Requests for External Resources

- **DNS Lookup**:
  - `resources.com`
  - `videos.com`
- **TCP/TLS Handshake** to each server
- **HTTP GET**:

`
GET /logo.png HTTP/1.1
Host: resources.com
`

`
GET /video.mp4 HTTP/1.1
Host: videos.com
`

- Servers respond with **200 OK** and content.

> Requests usually happen **in parallel** to speed up loading.

---

## 8️⃣ Caching Mechanism

- Browser stores:
  - Images, CSS, JS
- Based on headers:
  - `Cache-Control`, `Expires`
- On next visit, may **reuse cached resources** → reduces load, faster load times.

---

## 9️⃣ DOM Construction & Rendering

1. Build **DOM** from HTML
2. Apply **CSS**
3. Execute **JavaScript**
4. **Layout & Paint** → render content visually
5. Fully interactive page

---

## 🔟 Redirection Handling

- If a resource moved:
  - **301** → permanent redirect
  - **302** → temporary redirect
- Browser follows **Location header** automatically

---

## 1️⃣1️⃣ Fully Rendered Page

- HTML, CSS, images, videos, and scripts loaded
- Page is interactive
- Any asynchronous content continues loading

---

## ✅ Key Concepts

- **Ports**:
  - 53 → DNS
  - 80 → HTTP
  - 443 → HTTPS
- **Parallel Requests**: fetch multiple resources at once
- **Caching**: store resources to reduce server load
- **Status Codes**:
  - 200 OK → success
  - 301/302 → redirects
  - 403 → forbidden
  - 404 → not found
  - 500 → server error
- **CDN**: offloads static content closer to the user
- **TLS/HTTPS**: secure communication

---

## 🖼 Flow Diagram


<img width="1024" height="1536" alt="ChatGPT Image Jan 25, 2026, 02_17_30 PM" src="https://github.com/user-attachments/assets/8c379c30-a7b9-4a98-b00c-2883fd84b3fe" />

