# 🎓 Al Amal Program — Lecture & Progress Management System

> **Al Amal** (الأمل) means *"Hope"*. This is a single-file, offline-first dashboard for tracking a structured lecture program — built as a personal learning management system (LMS), not just a checklist.

A premium, modern, fully responsive dashboard that lives entirely in **one HTML file**. No installation, no server, no account, no internet connection required after download. Open it in any browser and your data is saved automatically on your own device.

---

## ✨ Why this exists

Structured programs (bootcamps, cohorts, self-study tracks) usually follow a repeating weekly rhythm — a fixed number of lectures per day, a rest day, and a weekly quiz. **Al Amal Program** is built around that exact rhythm:

| Day | Lectures |
|---|---|
| Sunday | 2 lectures |
| Monday | 2 lectures |
| Tuesday | 2 lectures |
| Wednesday | 2 lectures |
| Thursday | 2 lectures |
| Friday | 💤 OFF — Review Day |
| Saturday | 2 lectures + 🧪 Quiz |

That's **12 lectures + 1 quiz per week**, with Friday reserved for catching up and reviewing.

---

## 🖥️ Live Preview

Just download `al_amal_tracker.html` and double-click it — it opens directly in your browser (Chrome, Edge, Firefox, Safari). No build step, no `npm install`, nothing to configure.

---

## 🚀 Getting Started

### Option 1 — Download directly
1. Download [`al_amal_tracker.html`](./al_amal_tracker.html) from this repository.
2. Double-click the file (or right-click → *Open with* → your browser).
3. Go to **Settings** and set your **Start Date**, **Number of Weeks**, **Program Name**, and **Student Name**.
4. Click **Regenerate Weekly Structure** to build your schedule.
5. Start filling in lecture names/topics and tracking your progress.

### Option 2 — Clone the repository
```bash
git clone https://github.com/<your-username>/al-amal-program.git
cd al-amal-program
```
Then open `al_amal_tracker.html` in your browser — that's it. There is nothing to install.

> 💡 **Tip:** Bookmark the file or pin a shortcut to it so you can open your dashboard in one click every day.

---

## 📊 Features

### Dashboard
- Overview stat cards: overall progress, completed/remaining lectures, overdue lectures, quizzes completed, average quiz score, study streak, current week, and next lecture
- A signature **sunrise progress arc** — a custom SVG gauge that fills up as you complete lectures
- **Today's Focus** — automatically shows what's on your plate *today*, with one-tap "Mark Done" buttons
- **Friday Review Day** mode — dynamically pulls this week's hardest/unfinished lectures and any quiz issues so Friday actually helps you catch up
- **Saturday Quiz Day** mode — surfaces the day's lectures and the weekly quiz together
- **Overdue detection** — a banner and dedicated stat card flag lectures that fell behind schedule, with a one-click filter to review them
- Weekly mini-chart with the current week highlighted
- Recent activity feed

### Lectures
- Full CRUD (add / edit / delete / mark complete)
- Rich lecture detail modal: topic, difficulty, priority, duration, notes, learning objectives, key concepts, questions, and a completion checklist
- Search across name, topic, week, and notes
- Filter by status, week, day, and difficulty
- Sort by date, name, status, or priority
- Overdue lectures are visually flagged everywhere (table, calendar, modal)

### Quizzes
- Score tracking with automatic percentage calculation
- Average / highest / lowest score and completion-rate stats
- Status tracking (Not Taken, Needs Review, Passed, Retake) and weak-topic notes

### Schedule / Calendar
- Interactive weekly calendar matching the Sun–Thu / Friday-off / Saturday+quiz structure
- Click any lecture or quiz to open its details

### Weekly Progress
- Bar chart of completion % per week, with the current week highlighted
- **Pace indicator** — compares actual completion against how far each week *should* be based on today's date, flagging weeks that are 🔴 Behind vs 🟢 On track
- Per-week table: completed, remaining, overdue, completion %, and quiz score

### Notes
- Freeform standalone notes, separate from per-lecture notes

### Settings
- Program name, student name, start date, number of weeks, and passing quiz score — nothing is hard-coded
- Light / dark theme toggle
- **Export** your entire program as a JSON backup
- **Import** a previous backup to restore everything
- **Reset** the program with a confirmation dialog

---

## 🧠 Smart tracking logic

- **Accurate study streak** — counts consecutive scheduled study days you've completed, walking backward from today. Fridays and days with nothing scheduled don't break your streak, and today gets a grace period if you haven't finished it yet.
- **Current week detection** — correctly handles a program that hasn't started yet, is in progress, or has already finished, instead of just clamping a number.
- **Overdue lectures** — any lecture whose date has passed without being marked complete is automatically flagged across the dashboard, lecture table, and calendar.
- **Weekly pace** — each week's expected completion is calculated from how many of its lecture-days have already occurred, so you can see if you're ahead or behind *right now*, not just at the end of the week.

---

## 💾 Data & Privacy

- All data is stored **locally in your browser** using `localStorage` — nothing is ever sent to a server.
- Closing the browser or your laptop does not erase your progress; reopening the file picks up exactly where you left off.
- Use **Settings → Export Data** regularly to keep a JSON backup (e.g., in Google Drive or Dropbox), especially before clearing browser data or switching devices.
- Use **Settings → Import Data** to restore from a backup on a new device or browser.

---

## 🛠️ Tech Stack

- **Pure HTML, CSS, and JavaScript** — no frameworks, no build tools, no dependencies
- `localStorage` for persistence
- Inline SVG for the sunrise progress gauge and charts
- Fully responsive layout (desktop, tablet, and mobile — sidebar collapses, tables become cards)

---

## 📁 Project Structure

```
al-amal-program/
├── al_amal_tracker.html   ← the entire application (open this file)
└── README.md
```

Everything — markup, styles, and logic — lives in that single file by design, so it's trivial to download, share, or run from anywhere with zero setup.

---

## 🎨 Customization

Since lecture names/topics are intentionally left blank on first run, you control 100% of the content:
1. Open **Settings** and configure your program basics.
2. Go to **Lectures** and fill in names/topics as your program provides them, or edit them inline from the **Schedule** calendar.
3. Adjust difficulty/priority per lecture to power the Friday Review Day suggestions.

---

## 🤝 Contributing

Issues and pull requests are welcome. If you spot a bug or have an idea for a feature, feel free to open an issue.

## 📄 License

This project is available under the [MIT License](./LICENSE) — free to use, modify, and share.

---

<p align="center">Built to turn a weekly grind into a visible, motivating climb toward the sunrise. ☀️</p>
