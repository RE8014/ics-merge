# ICS Merge

A simple, automated setup that merges multiple iCalendar (`.ics`) files inside the `calendar/` directory into a single `calendar.ics` file at the root of the repository using GitHub Actions.

## 🚀 How It Works

1. Place or edit any `.ics` files inside the `calendar/` folder.
2. Every push or file change inside `calendar/` triggers a GitHub Action.
3. The Action collects all `VEVENT` entries across all files and merges them into a unified `calendar.ics` at the repository root.

---

## 📁 Repository Structure

```text
.
├── .github/
│   └── workflows/
│       └── merge-ics.yml     # The automated merge workflow
├── calendar/
│   ├── empty.ics             # Initial empty calendar template
│   ├── calendar-1.ics        # Your calendar files
│   └── calendar-2.ics
└── calendar.ics              # Auto-generated combined calendar file
