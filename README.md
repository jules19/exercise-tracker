# Exercise Tracker

This repository contains a small web-based exercise tracker. It lets you record daily workouts and plot your progress over time. The app stores data in [Firebase](https://firebase.google.com/), so you will need your own Firebase project to run it.

## 1. Set up Firebase

1. Go to the Firebase console and create a new project.
2. In the "Build" section, create a Firestore database.
3. On the project settings page, under **General**, find your web app configuration. It contains fields like `apiKey`, `authDomain`, and `projectId`.
4. Replace the sample configuration in [`index.html`](index.html) with your own values:

```javascript
// --- Firebase Configuration ---
const firebaseConfig = {
  apiKey: "<your-api-key>",
  authDomain: "<your-app>.firebaseapp.com",
  projectId: "<your-project-id>",
  storageBucket: "<your-app>.appspot.com",
  messagingSenderId: "<your-sender-id>",
  appId: "<your-app-id>"
};
```

The existing file shows where these lines live (around lines 204–212) for reference.

## 2. Serve the app locally

You can view the tracker by serving the `index.html` file with a simple static HTTP server. A quick method using Python is:

```bash
python3 -m http.server 8000
```

Then open `http://localhost:8000` in your browser.

Any static server will work, so you may also use tools like Node's `http-server` if preferred.

## Purpose

The exercise tracker helps you keep a log of workouts (squats, lunges, plank) and visualize them using charts. Data is saved in Firestore for persistence, so a Firebase project is required before you can log entries.
