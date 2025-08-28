# Q-PRE Starter (GitHub Pages + Firebase)

This package gives you a minimal working portal:
- Google Sign-In
- Role-based routing (Author / Reviewer / Editor) via Firestore `rolesByEmail`
- File upload to Firebase Storage (manuscripts & review reports)
- Basic Editor dashboard listing submissions

## Files
- `index.html` — sign-in + role-based redirect
- `upload-author.html` — author upload form
- `upload-reviewer.html` — reviewer report upload
- `editor.html` — minimal listing for editors
- `firestore.rules` — Firestore security rules
- `storage.rules` — Storage security rules

## Quick Setup
1. Create a Firebase project.
2. Enable **Authentication → Google** and add your site domains in **Authorized domains**.
3. Enable **Firestore (production mode)** and **Storage**.
4. In Firestore → `rolesByEmail`, add a document with ID = your email (editor) and body: `{ "role": "editor" }`.
5. Copy config from Firebase Web App and paste into each HTML file where indicated (`{{FIREBASE_CONFIG}}` block).
6. Publish rules:
   - Firestore → Rules → paste `firestore.rules` → **Publish**
   - Storage → Rules → paste `storage.rules` → **Publish**
7. Push to GitHub and enable Pages.

## Notes
- Authors only see their own uploads; reviewers only see their own reports; editors see everything.
- For downloads, start with Firebase Console; later you can add signed-URL buttons for editors.
