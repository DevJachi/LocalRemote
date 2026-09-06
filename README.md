# LocalRemote

LocalRemote is a lightweight **local-network remote control** that allows you to control your computer’s system volume from another device (such as a phone) over the same network.

(Built it cos my remote was busted and I was too lazy to get up and do it)

---

## 💡 What It Does

LocalRemote runs a small HTTP server on your computer and exposes endpoints that allow remote devices to:

- Increase system volume
- Decrease system volume
- Discover the host machine’s local IP address

Any device on the same network can trigger these actions using a browser or simple HTTP requests.

---

## 🧠 How It Works

1. An Express server runs locally on the host machine
2. System volume is accessed and controlled using OS-level APIs
3. Volume control endpoints are exposed over HTTP
4. Requests from devices on the same network trigger real-time volume changes

---

## 🛠 Tech Stack

- Node.js
- Express.js
- loudness (system volume control)
- CORS
- OS network interface utilities

---

## 📦 API Endpoints

## Increases system volume by 10% (capped at 100%)

```http
GET /volume/up
```

## Decreases system volume by 10%.

```
GET /volume/down
```
## Returns the local IP address of the host machine.
```
GET /ip
```
## ⚙️ Setup & Run
1. Clone the repository

2. Install dependencies
```
npm install
```
3. Start the server
   
4.
```
node index.js
```

## Open a browser on another device connected to the same network and visit:
```
http://<local-ip>:3000/volume/down
```

## 🔐 Notes
- LocalRemote is designed to run only on a trusted local network
- No authentication is implemented in the current version
- Intended for personal or controlled-network usage

## 🚀Future Improvements
- Authentication or access control
- Support for additional system controls (mute, play/pause, etc.)
- WebSocket support for real-time feedback

