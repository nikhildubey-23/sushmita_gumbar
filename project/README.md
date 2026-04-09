# Dr. Sushmita's Neurotherapy & Panchakarma Website

A modern, responsive medical website with appointment booking system built with Flask backend and vanilla JavaScript frontend.

## Project Structure

```
project/
├── frontend/
│   ├── index.html      # Main HTML file with all sections
│   └── script.js       # Frontend JavaScript logic
├── backend/
│   ├── app.py          # Flask application entry point
│   ├── config.py       # Configuration settings
│   ├── models.py       # SQLAlchemy database models
│   ├── routes/
│   │   ├── __init__.py
│   │   ├── appointments.py  # Appointment API routes
│   │   └── contact.py       # Contact form API routes
│   └── requirements.txt
└── README.md
```

## Tech Stack

### Frontend
- HTML5
- Tailwind CSS (CDN)
- Vanilla JavaScript
- Responsive design

### Backend
- Python Flask
- Flask-SQLAlchemy
- Flask-CORS
- PostgreSQL (Neon DB)

## Setup Instructions

### Prerequisites
- Python 3.9+
- PostgreSQL database (Neon DB recommended)
- Node.js (optional, for development)

### Backend Setup

1. Navigate to backend directory:
```bash
cd project/backend
```

2. Create virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install dependencies:
```bash
pip install -r requirements.txt
```

4. Set up environment variables (create `.env` file):
```env
FLASK_ENV=development
DATABASE_URL=postgresql://user:password@host:5432/dbname
SECRET_KEY=your-secret-key-here
```

5. Run the Flask server:
```bash
python app.py
```

The backend will run on `http://localhost:5000`

### Frontend Setup

Simply open `frontend/index.html` in a browser, or serve it with any static file server:

```bash
cd project/frontend
python -m http.server 8000
```

Access the frontend at `http://localhost:8000`

## Neon DB Setup

1. Create a Neon account at https://neon.tech
2. Create a new project
3. Get your connection string from the dashboard
4. Update the `DATABASE_URL` in your environment or `.env` file

Connection string format:
```
postgresql://username:password@ep-xxx-xxx-123456.us-east-2.aws.neon.tech/neondb?sslmode=require
```

## API Endpoints

### Appointments
- `GET /api/appointments` - Get all appointments
- `GET /api/appointments/<id>` - Get single appointment
- `POST /api/appointments` - Create new appointment
- `PUT /api/appointments/<id>` - Update appointment
- `DELETE /api/appointments/<id>` - Delete appointment
- `GET /api/appointments/stats` - Get appointment statistics

### Contact
- `POST /api/contact` - Submit contact message
- `GET /api/contact` - Get all messages
- `GET /api/contact/<id>` - Get single message
- `PUT /api/contact/<id>/read` - Mark message as read
- `DELETE /api/contact/<id>` - Delete message

## Features

- Modern dark theme with teal accents
- Fully responsive design
- Appointment booking system
- Contact form
- Treatment gallery with 17 therapies
- Doctor profile section
- Conditions treated section
- Wellness tips section
- Image gallery
- Floating WhatsApp button
- Smooth scroll animations
- Mobile-optimized navigation
- SEO-friendly HTML

## Treatments Available

1. Abhyanga - Full Body Massage
2. Hot/Fire Cupping
3. Kati Basti - Lower Back Treatment
4. Janu Basti - Knee Joint Treatment
5. Greeva Basti - Neck Treatment
6. Vamana - Therapeutic Emesis
7. Virechana - Purification Therapy
8. Raktamokshan - Blood Purification
9. Nasya - Nasal Therapy
10. Sarvanga Swedana - Full Body Steam
11. Agnikarma - Heat Therapy
12. Leech Therapy
13. Netra Tarpan - Eye Therapy
14. Shirodhara - Stress Relief
15. Shirobasti - Scalp Therapy
16. Acupuncture Needling
17. Swarnaprashan - Immunoboost

## Database Schema

### appointments
| Column | Type | Description |
|--------|------|-------------|
| id | Integer (PK) | Primary key |
| name | String(100) | Patient name |
| phone | String(20) | Phone number |
| treatment | String(100) | Selected treatment |
| date | Date | Appointment date |
| created_at | DateTime | Record creation timestamp |
| status | String(20) | Appointment status |

### contact_messages
| Column | Type | Description |
|--------|------|-------------|
| id | Integer (PK) | Primary key |
| name | String(100) | Sender name |
| phone | String(20) | Phone number |
| message | Text | Message content |
| created_at | DateTime | Record creation timestamp |
| is_read | Boolean | Read status |

## Deployment

### Backend (Render/Railway/Heroku)
1. Push code to GitHub
2. Connect repository to deployment platform
3. Set environment variables
4. Deploy

### Frontend
Deploy to Netlify, Vercel, or GitHub Pages as static files.

## Development Notes

- Frontend uses Tailwind CSS via CDN
- API calls are made to `http://localhost:5000/api`
- Update `API_BASE_URL` in `script.js` for production
- CORS is enabled for all origins (configure for production)
