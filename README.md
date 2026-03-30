# Intégra — Business Ethics Dashboard

**A single-file, browser-based business management dashboard focused on ethical business practices, with built-in analytics and data visualization.**

---

## 📦 What's Included

| File | Description |
|------|-------------|
| `integra-dashboard.html` | The complete dashboard — open in any browser, no server needed |

---

## 🚀 Quick Start

1. Download `integra-dashboard.html`
2. Open it in any modern browser (Chrome, Firefox, Edge, Safari)
3. No installation. No internet required after the first load.

> **Note:** The first load fetches Google Fonts and Chart.js from a CDN. After that, it works fully offline.

---

## 🗂️ Pages & Features

### 1. Dashboard Overview
The home screen showing a live summary of your organization.

- **4 Stat Cards** — Total Employees, Active Partners, Active Projects, and Overall Ethics Score
- **Ethics Principles Gauge** — 6 key principles (Transparency, Fairness, Accountability, Environmental Responsibility, Data Privacy, Community Impact) displayed as progress bars
- **Budget Overview Table** — All projects with budget allocation bars and impact scores
- **Department Pie Chart** — Staff distribution across departments (powered by Chart.js)
- **Activity Feed** — Real-time log of all actions taken in the dashboard

---

### 2. Analytics & Reports ⭐ New
A full analytics panel inspired by business intelligence tools (like Power BI).

| Chart | Type | What It Shows |
|-------|------|---------------|
| Ethics Score Trend | Line Chart | Monthly ethics score trajectory (6 months) |
| Department Headcount | Bar Chart | Number of employees per department |
| Partner Industries | Doughnut Chart | Industry breakdown of business partners |
| Project Status Mix | Pie Chart | Active vs. Planning vs. Completed projects |
| Ethics vs Performance | Scatter Plot | Correlation between ethics score and performance |
| Budget by Project | Horizontal Bar | Budget allocation per project (₱) |
| Employee Ethics Distribution | Histogram | How employees are distributed across score ranges |

**KPI Bar** at the top shows 5 live metrics:
- Total Budget (all projects combined)
- Average Employee Ethics Score
- Employee Active Rate (%)
- Partner Average Ethics Score
- Average Project Impact Score

**AI-Generated Insights** — An automatic analysis panel that reads your current data and surfaces:
- Whether ethics culture is strong or needs attention
- Employees who may benefit from additional training
- Partner risk flags
- Investment summary with impact commentary
- High-performing project highlights

---

### 3. Employee Management
Full CRUD (Create, Read, Update, Delete) for staff records.

**Fields per employee:**
- Full Name
- Department (Engineering, Marketing, Finance, Operations, HR, Legal & Compliance, Sales)
- Role / Position
- Ethics Training Score (0–100) — visualized as a color-coded progress bar
- Status (Active / Pending Onboarding / Inactive)

**Features:**
- Search by name, department, or role
- Color-coded ethics bars (green ≥85, amber 65–84, red <65)
- Status pills with live indicators
- Edit and Delete with confirmation dialog

---

### 4. Business Partners
Track and assess business partners with ethics due diligence scoring.

**Fields per partner:**
- Organization Name
- Industry
- Contact Person
- Ethics Rating (0–100) — from due diligence assessments
- Status (Active / Under Review / Inactive / Flagged for Review)

**Features:**
- Flagged partners trigger a warning notification
- Same search, edit, and delete capabilities as employees

---

### 5. Project Management
Manage projects with a focus on social impact alongside financial metrics.

**Fields per project:**
- Project Name
- Team Lead
- Budget (₱ Philippine Peso)
- Social Impact Score (0–100)
- Status (Active / Planning / Completed)

**Features:**
- Budget formatted in ₱ with locale-aware number formatting
- Impact score visualized as a color-coded bar
- Same CRUD and search capabilities

---

### 6. Ethics & Compliance Center
The ethics hub for your organization.

**6 Core Ethics Principles** displayed as reference cards:
1. 🌿 Environmental Stewardship
2. ⚖️ Fairness & Non-Discrimination
3. 🔍 Transparency & Honesty
4. 🛡️ Data Privacy & Security
5. 🤲 Community Responsibility
6. 📣 Whistleblower Protection

**Compliance Log** — Log and track compliance events with:
- Category (Data Privacy, Environmental, Labor Rights, Financial Integrity, Anti-Corruption, Whistleblower Report, Supplier Ethics)
- Reporter name (or "anonymous")
- Description
- Resolution status (Under Review / Resolved / Escalated)

---

## 🛠️ Technical Details

| Feature | Technology |
|---------|------------|
| Charts & Graphs | [Chart.js 4.4.1](https://www.chartjs.org/) via CDN |
| Fonts | DM Serif Display + DM Sans (Google Fonts) |
| State Management | Vanilla JavaScript (in-memory) |
| Storage | None — data resets on page refresh |
| Framework | Pure HTML + CSS + JS (no build step) |
| File Size | ~1 single file |

---

## 💾 Data Persistence

> ⚠️ **Important:** Data is stored in-memory only. Refreshing the page resets all data to the sample defaults.

**To save your data**, you have a few options:

### Option A — Export to JSON (easy)
Open the browser console (`F12 → Console`) and type:
```javascript
copy(JSON.stringify(state, null, 2))
```
Paste the result into a `.json` file. To restore, paste it back and run:
```javascript
Object.assign(state, YOUR_PASTED_DATA); renderAll();
```

### Option B — Add localStorage (for developers)
Replace the `renderAll()` call at the bottom of the script with:
```javascript
// Save
localStorage.setItem('integra', JSON.stringify(state));

// Load on startup
const saved = localStorage.getItem('integra');
if (saved) Object.assign(state, JSON.parse(saved));
renderAll();
```

### Option C — Connect a backend
Replace the `state` object with API calls to any REST backend (Node.js, PHP, Python/Flask, etc.).

---

## 🎨 Customization

### Change the color theme
Edit the CSS variables at the top of the `<style>` block:
```css
:root {
  --accent: #2d5a3d;   /* Primary green */
  --accent2: #4a8c60;  /* Secondary green */
  --gold: #c4973a;     /* Gold/amber accent */
  --danger: #c0392b;   /* Red for warnings */
  --bg: #f5f3ee;       /* Page background */
}
```

### Add more departments
Find the `<select id="emp-dept">` in the Employee Modal and add `<option>` tags.

### Add more compliance categories
Find `<select id="comp-cat">` in the Compliance Modal and add options.

### Change the currency
Search for `₱` in the file and replace with your preferred currency symbol.

### Change the date locale
Search for `en-PH` and replace with your locale code (e.g., `en-US`, `en-GB`).

---

## 🔐 Ethics & Privacy Notes

This dashboard was built with ethical data handling in mind:

- No data is sent to any server or third party
- No cookies, no tracking, no analytics calls
- Employee records display a confidentiality notice
- Partner records require ethics due diligence scores
- Compliance entries support anonymous reporting
- All deletions require explicit confirmation

---

## 📋 Sample Data

The dashboard loads with sample data so you can explore immediately:

- **7 Employees** across Engineering, HR, Finance, Operations, Marketing, Sales, and Legal
- **4 Partners** across Technology, Logistics, Education, and Healthcare
- **5 Projects** with a mix of statuses and budgets
- **0 Compliance entries** (intentionally empty — a good sign!)

---

## 🖥️ Browser Support

| Browser | Supported |
|---------|-----------|
| Chrome 90+ | ✅ |
| Firefox 88+ | ✅ |
| Edge 90+ | ✅ |
| Safari 14+ | ✅ |
| IE 11 | ❌ |

---

## 📈 Roadmap / Possible Enhancements

- [ ] Export data to CSV / Excel
- [ ] PDF report generation
- [ ] localStorage / IndexedDB persistence
- [ ] Role-based access (admin vs. viewer)
- [ ] Email alerts for flagged partners or low ethics scores
- [ ] Dark mode toggle
- [ ] Multi-language support (Filipino / English toggle)
- [ ] Integration with HR systems (BambooHR, Workday)

---

## 🤝 License

This is a custom single-file dashboard. Use it freely for your business or organization. Attribution appreciated but not required.

---

*Built for ethical business leaders who believe doing right and doing well are not opposites.*
