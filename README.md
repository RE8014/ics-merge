# Private ICS Calendar Merger

Automatically merges multiple iCalendar (`.ics`) files inside the `calendar/` folder into a single `calendar.ics` published directly to a **Secret GitHub Gist**.

## 🚀 How It Works

1. Add, modify, or remove `.ics` files in the `calendar/` folder.
2. Pushing changes triggers a GitHub Action that parses all `VEVENT` entries across your calendar files.
3. The workflow patches the combined calendar directly to your private, unlisted GitHub Gist via API.

---

## 📂 Project Structure

```text
.
├── .github/
│   └── workflows/
│       └── merge-ics.yml     # Auto-merge and Gist sync workflow
└── calendar/
    ├── empty.ics             # Base calendar template
    ├── calendar-1.ics
    └── calendar-2.ics

```

---

## ⚙️ Setup Instructions

### 1. Create a Secret Gist

1. Go to [gist.github.com](https://gist.github.com).
2. Create a file named `calendar.ics` with basic `.ics` structure and click **Create secret gist**.
3. Copy the **Gist ID** from the URL (`https://gist.github.com/username/`**`GIST_ID`**).

### 2. Configure Repository Secrets

Go to **Settings** > **Secrets and variables** > **Actions** in this repository and add:

* `GIST_ID`: Your Secret Gist ID.
* `GIST_TOKEN`: A GitHub Personal Access Token (classic) with the `gist` permission scope enabled.

---

## 🔗 Calendar Subscription

1. Open your Secret Gist page and click the **Raw** button on `calendar.ics`.
2. Copy the resulting URL into Apple Calendar, Google Calendar, or Outlook to subscribe.
