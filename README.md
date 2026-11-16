# Tuition Register

A small phone app to track tuition attendance, class time and the fees due to each teacher.

- Add teachers with a **per hour** or **per day** rate
- Mark **Attended** and enter the time the class ran; the duration and fee are worked out automatically
- Mark **Absent**, **Teacher on leave** or **Holiday** (no fee)
- Record payments (Cash / UPI / Bank); "Due now" goes down
- Works offline and installs to the home screen

Data is stored on the phone (browser storage). Use **Save backup** regularly and keep the file somewhere safe; **Restore backup** loads it back, also on a new phone.

## Put it online with GitHub Pages
1. Create a new public repository on github.com (e.g. `tuition-tracker`).
2. Click **Add file → Upload files** and upload all files from this folder.
3. Go to **Settings → Pages**, set Source to **Deploy from a branch**, branch **main**, folder **/ (root)**, and save.
4. After a minute the app is live at `https://<your-username>.github.io/tuition-tracker/`.
5. Open that link on the phone in Chrome → menu → **Add to Home screen** (on iPhone: Safari → Share → **Add to Home Screen**).

When you change `index.html` later, also change `VERSION` in `sw.js` so phones pick up the new version.
