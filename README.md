# SmartSpend

SmartSpend is a full-stack credit card budgeting and spending tracker built to help users monitor card usage, manage budgets, and receive AI-powered financial recommendations. The app combines a Flask backend with a React frontend to provide a clean, responsive spending dashboard.

## Features

- User sign up and login
- Session-based authentication
- Add, update, and delete credit cards
- Track spending against each card's budget
- Set reset periods for card budgets
- Automatic spending resets based on monthly or yearly cycles
- AI-generated financial recommendations using OpenAI
- Download card data as an Excel file
- Responsive dashboard interface

## Tech Stack

### Frontend
- React
- Vite
- React Router
- CSS

### Backend
- Python
- Flask
- Flask-SQLAlchemy
- SQLite
- OpenAI API

## Project Structure

```text
smart-spend-fullstack/
├── backend/
│   ├── __pycache__/
│   ├── instance/
│   │   └── mydatabase.db
│   ├── ai_routes.py
│   ├── auth_routes.py
│   ├── card_routes.py
│   ├── config.py
│   ├── main.py
│   ├── models.py
│   ├── requirements.txt
│   └── .gitignore
├── frontend/
│   ├── src/
│   ├── package.json
│   ├── package-lock.json
│   ├── vite.config.js
│   ├── eslint.config.js
│   ├── index.html
│   └── .gitignore
├── README.md
└── .gitignore
```

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/nicolasona1/smart-spend-fullstack.git
cd smart-spend-fullstack
```

### 2. Set up the backend

```bash
cd backend
python -m venv .venv
source .venv/bin/activate   # On Windows: .venv\Scripts\activate
pip install -r requirements.txt
```

Create a `.env` file in the `backend` folder:

```env
OPENAI_API_KEY=your_openai_api_key_here
OPENAI_MODEL=gpt-4o-mini
```

Start the backend:

```bash
python main.py
```

The backend runs locally at:

```text
http://localhost:5002
```

### 3. Set up the frontend

Open a new terminal and run:

```bash
cd frontend
npm install
npm run dev
```

The frontend dev server runs at:

```text
http://localhost:5173
```

## API Overview

### Authentication
- `POST /sign_up` — Create a new user
- `POST /login` — Login a user
- `POST /logout` — Logout a user

### Card Management
- `GET /user_cards` — Retrieve all cards for the logged-in user
- `POST /add_cards` — Add a new credit card
- `PATCH /update_spent/<card_id>` — Update the amount spent on a card
- `DELETE /delete_cards/<card_id>` — Delete a card
- `PATCH /update_reset_period` — Update budgeting reset period for user cards

### AI Recommendations
- `POST /ai/recommendation` — Generate personalized financial recommendations
- `GET /ai/test` — Check AI connectivity

### Excel Export
- `GET /download_excel` — Download card data as an Excel spreadsheet

## App Workflow

1. User creates an account or logs in.
2. User adds credit cards with budget and bank information.
3. Spending is tracked against each card's budget.
4. The app resets spending automatically based on the selected reset cycle.
5. AI analyzes spending patterns and generates suggestions.
6. Users can export their current spending summary as an Excel file.

## Environment Notes

- The backend uses SQLite and creates tables automatically when the app starts.
- OpenAI integration requires a valid API key in `backend/.env`.
- The project is intended for local development and personal finance tracking.

## License

This project does not currently include a license file. If you plan to share or publish the repository publicly, consider adding an open-source license such as MIT.

## Contributing

Contributions are welcome. To contribute:

```bash
git checkout -b feature/your-feature
git commit -m "Add your feature"
git push origin feature/your-feature
```

Then open a pull request on GitHub.

## Contact

For questions or collaboration, reach out through the repository owner on GitHub.
