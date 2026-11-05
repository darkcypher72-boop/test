# ELVIAN — Learn more. Work smart.

## About the developer

**Master Tonmoy Kumar Deb** is currently pursuing a Bachelor of Technology in Computer Science and Engineering. He is a student who loves turning ideas into working software, and his goal is to become a skilled software developer. He works with HTML5, CSS3, JavaScript, React, Python, C, C++ and MySQL, and he is always adding new things to his toolbox.

In August 2026 he participated in the Smart India Hackathon (SIH), one of the biggest student innovation competitions in the country. He believes the best way to learn is to build real things, share them, and keep improving them.

- Instagram: [@tonmoy_deb339](https://www.instagram.com/tonmoy_deb339/)
- LinkedIn: [Tonmoy Kumar Deb](https://www.linkedin.com/in/tonmoy-kumar-deb-45b4a9449/)

## About Elvian

**Elvian** was made for gaining knowledge. It is a friendly assistant that helps you learn, understand and work smart. It explains things clearly in simple language, solves mathematics with real symbols, draws graphs for any function, shows pictures and animated diagrams where a picture explains better than words, and reads your files and photos so you can ask questions about them.

The idea behind Elvian is simple: your time should go into learning and creating, not into searching and repeating. Ask a question, attach a document, set a timer, make a QR code or a presentation, and Elvian helps you finish faster and understand more. When you ask who made it, Elvian says: *"I'm Elvian, developed by Master Tonmoy Kumar Deb for gaining knowledge and working smart."*

## 1. Files and where they go

| File / folder | What it is | Upload to GitHub? |
|---|---|---|
| `index.html` | Splash screen (3D intro) | ✅ Yes |
| `e-ELVIAN.html` | The Elvian chatbot | ✅ Yes |
| `physical-elvian.html` | Physical ELVIAN page | ✅ Yes |
| `assets/tonmoy.jpg` | Your photo for the About card (add it yourself) | ✅ Yes |
| `server.js` | Optional backend (lock code, prompt counter, AI key) | ✅ Safe to upload, but it **cannot run on GitHub Pages** |
| `.env` | **Your secrets** (lock-code hash and backend settings) | ❌ **NEVER** (`.gitignore` blocks it) |
| `.env.example` | Empty template of `.env` | ✅ Yes |
| `.gitignore` | Tells Git to skip secrets | ✅ Yes |
| `state.json` | Created by the backend (prompt counts) | ❌ Never (ignored) |

Keep the three `.html` files in the **same folder** so the links between them work.

### Add your photo
Save your photo as `assets/tonmoy.jpg` (any shape works; the whole picture is shown, nothing is cropped). Until then the About card shows the initials "TK".

### Upload to GitHub Pages
1. Create a repository and upload the three `.html` files, the `assets` folder, `.gitignore`, `.env.example`, `README.md` and `server.js`.
2. Repository → Settings → Pages → deploy from the `main` branch, root folder.
3. Your site is `https://YOURNAME.github.io/REPO/`.

> Before every upload, check that `.env` is **not** in the list of files. If it ever goes up by mistake, change your lock code immediately.

## 2. The lock / unlock code

- Every chat allows **50 prompts**. A reminder appears at 40, and at 50 the chat locks.
- **Alt+K** (or the lock pop-up) asks for the secret code to unlock a chat (+50 prompts) or lock it.
- The code is **never in the web page**. `.env` stores only a salted scrypt **hash** of it.
- To change the code run `node server.js --hash "new code"`, then copy the printed `UNLOCK_CODE_HASH=...` line into `.env`.
- Wrong guesses are limited to 5 per 15 minutes per person.

### Run the backend (needs Node.js 18 or newer)
1. Open `.env` and set `ALLOWED_ORIGIN` to your site address, for example `https://yourname.github.io` (use `null` only for testing on your own PC).
2. Optional: set `LLM_URL`, `LLM_KEY` and `LLM_MODEL` so your AI key stays on the server.
3. In this folder run `node server.js`.
4. Host it somewhere that runs Node (Render, Railway, Fly.io or your own PC) and paste its address in **e-ELVIAN → Settings → Secure backend**.

## 3. How each feature works

| Feature | How to use it |
|---|---|
| Chat history | Left sidebar. Hover a chat → **⋯** → Rename / Delete. Every reload opens a fresh chat. |
| Dark / light, background | Settings. 7 built-in scenes, your own image (with preview and remove), dimming, slideshow (**Alt+L**). |
| Attach | **+** → camera or device. Reads pictures, PDF, Word, PowerPoint, Excel, OpenDocument, RTF, ZIP, code and text, audio/video details, and any other file (nothing is refused). |
| Pictures | Real reference photos (with credit) when Elvian adds a `[[pic: …]]` request or you ask for pictures. "Generate an image of …" makes an AI picture. |
| Diagrams and graphs | Animated explainers (for example how current flows in a circuit), graphs for any function, bar, line and pie charts. |
| Files Elvian creates | Ask "make a ppt / Word / Excel / PDF on …". |
| QR code | "generate qr for …" |
| Timer | "set a timer for 10 minutes". It rings with sound when done. |
| Voice | The speaker button reads an answer (male Indian-English voice, word highlight). The mic (**Alt+M**) stops after 3 seconds of silence and you press Send. |
| Saved messages | Bookmark button under any message. **Ctrl+H** opens the list; the arrow jumps to that chat. |
| Google sign-in | Put your Client ID in `gid:''` near the top of `e-ELVIAN.html` and add your site address under *Authorised JavaScript origins* in Google Cloud Console. |

### Shortcuts
Enter send · Shift+Enter new line · Alt+N new chat · Ctrl+S sidebar · Ctrl+F full screen · Ctrl+H saved · Alt+D theme · Alt+S settings · Alt+M mic · Alt+L slideshow · Alt+K lock/unlock · Alt+↑ edit last · `/` focus the box · Esc stop · Ctrl+/ list of shortcuts.

## 4. Troubleshooting
- **"The free AI is busy"** – the free service is rate-limited and Elvian retries by itself. Add your own key in Settings for more speed.
- **No Indian male voice** – Windows: Settings → Time & language → Speech → add *English (India)* (Ravi / Prabhat). Edge has the best voices.
- **Photo missing in About** – add `assets/tonmoy.jpg`.
- **Google sign-in asks for a Client ID** – follow the Google sign-in row above.
