Scope Technologies - Online Exam Portal (online version)
========================================================
Students can give the exam on ANY device. Results are saved on the server and appear in
Admin -> Results automatically (refreshes every 8 seconds). No Result Code / WhatsApp pasting needed.

Folder
  public/index.html, css/style.css, js/script.js, images/logo.png   -> website
  netlify/functions/api.mjs                                         -> backend (storage + grading)
  netlify.toml, package.json                                        -> Netlify settings

DEPLOY ON NETLIFY (GitHub method - easiest)
  1. Create a GitHub repo and upload ALL these files (keep the folder structure).
  2. Netlify -> Add new site -> Import an existing project -> GitHub -> choose the repo.
     Build command: (leave empty)   Publish directory: public   (netlify.toml already sets this)
  3. Site configuration -> Environment variables -> Add:  ADMIN_PASSWORD = your-own-password
     Then Deploys -> Trigger deploy -> Deploy site.
  4. Open your site -> Admin -> login with that password.

DEPLOY WITH NETLIFY CLI (no GitHub)
  npm install
  npm install -g netlify-cli
  netlify login
  netlify init            (or: netlify link)
  netlify env:set ADMIN_PASSWORD your-own-password
  netlify deploy --prod

NOTE: Drag & drop deploy does NOT run the backend function, so use one of the two methods above.

Using it
  Admin -> New Exam: type questions or import Excel/CSV (see sample files in public/).
  Admin -> Students & Links: add a student, then Copy Link / WhatsApp. The link opens on any device.
  Admin -> My Exams -> "Copy exam link": one common link; students type their own name/roll.
  Admin -> Results: live results, view each answer, delete (lets a student retry), download CSV.
  Typed answers: case-insensitive. Several accepted answers: write them as  Delhi | New Delhi
  Leaving the exam tab/window ends the exam immediately and submits the answers given so far.
