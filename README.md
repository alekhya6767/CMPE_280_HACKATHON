# BookTableBuddy

**BookTableBuddy** is a CMPE 280 team project: an end-to-end restaurant reservation platform (OpenTable-style). Customers search restaurants, view details and maps, and manage bookings. Restaurant managers run dashboards, tables, hours, and photos. Admins approve restaurants and view system analytics.

## Team members

- VIJAYA SHARAVAN REDDY BADDAM - 018321342
- JAYANTH SAI YARLAGADDA - 018291819
- DIVYASRI LAKSHMI ALEKHYA NAKKA - 018291702

## Features

- **Customers:** Search, restaurant detail, booking flow, my bookings, confirmation pages, Google Maps integration.
- **Restaurants:** Dashboard, booking management, calendar, profile, tables, hours, photos, analytics-oriented views.
- **Admins:** Approvals, user and restaurant management, analytics.
- **API:** Django REST with JWT (`djangorestframework-simplejwt`), grouped under `/api/users/`, `/api/restaurants/`, `/api/bookings/`, `/api/analytics/`.
- **Notifications:** Email (e.g. SendGrid) and SMS-related integrations (Twilio) in the backend; see `requirements.txt` and `bookings` app.

## Tech stack

| Layer | Technology |
|--------|------------|
| Frontend | React 18, React Router, Axios, Tailwind CSS, Create React App, `@react-google-maps/api` |
| Backend | Python 3, **Django 5**, **Django REST Framework**, JWT, **SQLite** (default; PostgreSQL optional in settings) |
| Tooling | Postman-style collections in `BookTableBuddy/` (`*_API_Collection.json`), Replit metadata optional |

## Repository layout

```
CMPE_280_HACKATHON/
├── README.md                 # This file
├── BookTableBuddy/
│   ├── backend/              # Django project (`manage.py`, `booktable` settings)
│   ├── frontend/             # React app (`npm start` → port 3000, proxies API to :8000)
│   ├── CHANGELOG.md
│   └── *_API_Collection.json # API collections for testing
└── Diagrams/                 # Wireframes and architecture images
```

## Local development

### Backend

```bash
cd BookTableBuddy/backend
python -m venv .venv
source .venv/bin/activate   # Windows: .venv\Scripts\activate
pip install -r requirements.txt
python manage.py migrate
python manage.py runserver 8000
```

Optional: create a `.env` in `backend/` for `SECRET_KEY`, `DEBUG`, and any email/SMS keys your team uses (`python-dotenv` is loaded in `booktable/settings.py`).

### Frontend

```bash
cd BookTableBuddy/frontend
npm install
npm start
```

The dev server runs on **port 3000** and proxies API requests to **http://localhost:8000** (`package.json` `proxy`).

### Quick API check

With the backend running, open **http://127.0.0.1:8000/** — the root route returns a small JSON index of main API paths.

## Documentation and changelog

- **`BookTableBuddy/CHANGELOG.md`** — release notes and recent fixes (e.g. restaurant approval flow).
- **Wireframes / diagrams** — under `Diagrams/` and `Diagrams/Wireframes/`.

## License / course use

Built for CMPE 280 coursework; use and distribution follow your course and team agreement.
