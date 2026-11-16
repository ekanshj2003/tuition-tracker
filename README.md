# Tuition Register

A phone app to track tuition attendance, class time and the fees due to each teacher.

- Add teachers with a **per hour** or **per day** rate
- Tap **Attended** and enter the time the class ran; class time and fee are worked out automatically
- Mark **Absent**, **Teacher on leave** or **Holiday** (no fee)
- Record payments (Cash / UPI / Bank); "Due now" goes down
- **Syncs between phones** through your own Google Sheet (free)
- Works offline; changes made offline sync when the phone is back online

---

## Part 1 – Put the app on GitHub Pages (once)
1. On github.com create a new **public** repository, e.g. `tuition-tracker`.
2. **Add file → Upload files** → upload every file from this folder (you can skip `google-sheet-sync.gs`).
3. **Settings → Pages** → Source: **Deploy from a branch**, branch **main**, folder **/ (root)** → Save.
4. After a minute the app is at `https://<your-username>.github.io/tuition-tracker/`.
5. On each phone open that link → Chrome menu → **Add to Home screen**
   (iPhone: Safari → Share → **Add to Home Screen**).

## Part 2 – Set up sync with a Google Sheet (once, ~5 minutes)
1. Go to sheets.google.com and create a blank sheet, name it `Tuition Register Data`.
2. In the sheet: **Extensions → Apps Script**.
3. Delete what's there, paste the whole contents of `google-sheet-sync.gs`.
4. On the line `const SECRET = "change-this-secret";` replace `change-this-secret` with your own secret word (e.g. `jain-tuition-4821`). Click **Save**.
5. Click **Deploy → New deployment** → gear icon → **Web app**.
   - Execute as: **Me**
   - Who has access: **Anyone**
   - Click **Deploy**, then **Authorize access** and allow it with your Google account
     (if you see "Google hasn't verified this app": **Advanced → Go to … (unsafe)** — it's your own script).
6. Copy the **Web app URL** (starts with `https://script.google.com/macros/s/…/exec`).

## Part 3 – Connect each phone
In the app, scroll down → **Set up sync** → paste the Web app URL and your secret word → **Save and sync**.
Do the same on every phone. Records already on a phone are uploaded when you connect it.

The app syncs automatically after every change, when you open it, and every 30 seconds while open.
All records are visible in the `data` tab of your Google Sheet. Don't edit that tab by hand.

Keep the URL and secret word private: anyone with both can see and change the records.

---

### Updating the app later
After uploading a new `index.html`, change `VERSION` in `sw.js` (e.g. `tuition-v3`) so phones load the new version.
If you change the Google script, use **Deploy → Manage deployments → Edit → Version: New version** so the URL stays the same.
