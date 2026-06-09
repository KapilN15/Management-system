# Heartfulness NGO Management System

A complete localhost Flask + SQLite application for staff-only NGO operations: authentication, dashboard notifications, dynamic categories, member category assignment, CSV import/export, category-linked sessions, category-based attendance, session summaries, category analytics, reports, audit logs, backup/restore, global search, and persistent light/dark theme.

## Setup

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
python run.py
```

Open `http://127.0.0.1:5000`. For Wi-Fi access, open `http://YOUR_LOCAL_IP:5000` from another device on the same network.

The SQLite database is created automatically in `instance/heartfulness.db`.

## Default Users

- Super Admin: `sa1` / `passsa1`
- Admin: `ad1` / `passad1`, `ad2` / `passad2`
- Coordinator: `co1` / `passco1`, `co2` / `passco2`
- Trainer: `tr1` / `passtr1`, `tr2` / `passtr2`, `tr3` / `passtr3`, `tr4` / `passtr4`, `tr5` / `passtr5`

## CSV Import Columns

`full_name,gender,age,religion,mobile_number,area,join_date,status,category`

Use `YYYY-MM-DD` dates. Area is converted to uppercase. Category can contain one or many existing category names, separated by commas. Quote multi-category values, for example:

```csv
full_name,gender,age,religion,mobile_number,area,join_date,status,category
Priya Kumar,Female,31,Hindu,9999999999,hosur,2026-06-09,Active,"Meditation, Youth"
```

## Workflow

Create Category -> Register Member -> Assign Category -> Create Session -> Select Session Category -> Load Eligible Members -> Mark Attendance -> View Session Summary -> Reports -> Category Analytics -> Audit Logs.
