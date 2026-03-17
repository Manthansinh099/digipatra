# DigiPatra — Unified Citizen Document Portal
### Government of Gujarat · NIC · React Project

---

## 🚀 Quick Start

```bash
# 1. Install dependencies
npm install

# 2. Start development server
npm start

# 3. Build for production
npm run build
```

Open [http://localhost:3000](http://localhost:3000) in your browser.

---

## 📁 Project Structure

```
digipatra/
├── public/
│   └── index.html
├── src/
│   ├── App.js                    ← Root router
│   ├── index.js                  ← Entry point
│   ├── styles/
│   │   └── global.css            ← All CSS variables, base styles
│   ├── data/
│   │   ├── constants.js          ← Departments, doc types, admin
│   │   ├── dummyData.js          ← Seed data (citizens, docs, etc.)
│   │   └── translations.js       ← EN / HI / GU strings
│   ├── context/
│   │   ├── AppContext.js         ← Global state + all actions
│   │   └── LangContext.js        ← Translation hook
│   ├── utils/
│   │   └── helpers.js            ← uid, fmtAadhaar, download, share, etc.
│   ├── components/
│   │   ├── Logo.jsx              ← DigiPatra SVG logo
│   │   ├── LangBar.jsx           ← EN/हि/ગુ toggle
│   │   ├── Navbar.jsx            ← Top navigation bar
│   │   └── DocModal.jsx          ← Citizen document view modal
│   └── pages/
│       ├── Landing.jsx           ← Role selection screen
│       ├── LoginPage.jsx         ← Login (citizen / officer / admin)
│       ├── RegisterPage.jsx      ← Citizen self-registration
│       ├── CitizenDashboard.jsx  ← Citizen document view
│       ├── OfficerDashboard.jsx  ← Officer upload + update requests
│       └── AdminDashboard.jsx    ← Admin full system view
└── package.json
```

---

## 🔐 Demo Credentials

### Citizen Login (Aadhaar or Mobile + OTP: **123456**)
| Name | Aadhaar | Mobile |
|------|---------|--------|
| Aarav Shah | 2345 6789 0123 | 9988776655 |
| Priya Desai | 3456 7890 1234 | 9977665544 |
| Rohan Patel | 4567 8901 2345 | 9966554433 |

### Officer Login (password: **officer123**)
| Name | Department | Mobile |
|------|-----------|--------|
| Ramesh Patel | UIDAI | 9876543210 |
| Sunita Sharma | RTO | 9876543211 |
| Arvind Mehta | Education Board | 9876543212 |
| Kavita Joshi | Municipality | 9876543213 |
| Deepak Verma | PDS Dept | 9876543214 |
| Priya Singh | Health Dept | 9876543215 |
| Nikhil Gupta | Revenue Dept | 9876543216 |

### Super Admin
| Mobile | Password |
|--------|----------|
| 9000000001 | admin@2024 |

---

## ✅ Features

### Citizen
- OTP login via Aadhaar or Mobile
- View all documents with department colour coding
- Search and filter by department
- Download document as formatted HTML (print-to-PDF)
- Share document link
- **✏️ Request Update** — select field, enter new value + reason → officer notified
- **⚑ Flag Error** — flag wrong document → officer notified
- Bell notification panel with unread count

### Officer
- 3-step document upload: Find Citizen → Select Doc Type → Fill Fields
- View all records uploaded by own department
- **✏️ Update Requests tab** — review citizen requests, edit any field, approve or reject
- 🔔 Alerts tab — flag notifications + update request notifications

### Super Admin
- System overview with live stats
- All Citizens — expandable, click doc chips to open
- All Documents — searchable, clickable
- Officers — activate / deactivate
- Audit Log — filterable by action type
- User Management — create officers, create citizens, deactivate accounts

---

## 🌐 Languages
English · हिन्दी · ગુજરાતી — toggle on every screen

---

## 🛠️ Tech Stack
- React 18 (Create React App)
- Context API for state management
- Pure CSS (no CSS-in-JS, no Tailwind)
- No backend — all data in-memory

---

## 🚀 Production Mapping
| Demo | Production |
|------|-----------|
| OTP "123456" | UIDAI OTP API / Twilio |
| In-memory arrays | PostgreSQL + Redis |
| HTML download | Server-side PDF (Puppeteer) |
| Mock share link | Short URL service + JWT |
