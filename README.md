# ⚽ FIFA World Cup 2026 — Macy Predictor Challenge

Live site: **https://mmacy01.github.io/wc2026-macy/**

---

## Setup Checklist

### ✅ Step 1 — Create Firebase Project (separate from AmSty)
1. Go to **https://console.firebase.google.com**
2. Click **Add project** → name it `wc2026-macy` → **Continue** → disable Analytics → **Create project**
3. Click **Build** → **Firestore Database** → **Create database** → **Start in test mode** → **us-central1** → **Enable**
4. Click **Firestore Database** → **Rules** tab → replace everything with:
```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if request.time < timestamp.date(2026, 8, 31);
    }
  }
}
```
Click **Publish**

5. Click ⚙️ **Project settings** (gear icon top left)
6. Scroll to **Your apps** → click **</>** Web icon
7. Name it `wc2026-macy-web` → click **Register app**
8. Copy the 6 values from the config block that appears

---

### ✅ Step 2 — Paste Firebase Config into index.html
1. Open `index.html` in Notepad
2. Find this block near the top of the `<script>` section:
```javascript
var FIREBASE_CONFIG = {
  apiKey:            "PASTE_YOUR_API_KEY_HERE",
  authDomain:        "PASTE_YOUR_PROJECT_ID.firebaseapp.com",
  projectId:         "PASTE_YOUR_PROJECT_ID",
  storageBucket:     "PASTE_YOUR_PROJECT_ID.firebasestorage.app",
  messagingSenderId: "PASTE_YOUR_SENDER_ID",
  appId:             "PASTE_YOUR_APP_ID"
};
```
3. Replace each `PASTE_YOUR_...` with your real values
4. Save the file

---

### ✅ Step 3 — Create GitHub Repo
1. Go to **github.com** → sign in as **mmacy01**
2. Click **+** → **New repository**
3. Name it exactly: `wc2026-macy`
4. Set to **Public**
5. Click **Create repository**
6. Click **uploading an existing file**
7. Drag in `index.html`, `README.md`, and the `.github` folder
8. Click **Commit changes**

---

### ✅ Step 4 — Enable GitHub Pages
1. Click **Settings** → **Pages** (left sidebar)
2. Under **Source** → select **Deploy from a branch**
3. Under **Branch** → select **main** and **/ (root)**
4. Click **Save**
5. Wait 2 minutes → go to `https://mmacy01.github.io/wc2026-macy/`

---

## 🔐 Admin Access
- Click **Admin** tab on the site
- Password: `Macychallenge`
- Green dot = Firebase connected, submissions flow in real time

## 📋 Scoring (max 189 pts)
| Round | Points |
|---|---|
| Group Stage Winner | 1 pt × 12 = 12 |
| 3rd Place Qualifier | 2 pts × 8 = 16 |
| Round of 32 | 3 pts × 16 = 48 |
| Round of 16 | 5 pts × 8 = 40 |
| Quarterfinals | 7 pts × 4 = 28 |
| Semifinals | 10 pts × 2 = 20 |
| Final Winner | 15 pts |
| Champion Bonus | +10 pts |
| **Maximum** | **189 pts** |
