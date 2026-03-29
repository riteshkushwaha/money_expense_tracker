# Money Expense Tracker

A Flask-based web application for tracking and managing personal expenses. This project is structured as an educational learning path with progressive feature development.

## Features

- **User Authentication**: Register, login, and logout functionality
- **Expense Management**: Add, edit, and delete expenses
- **User Profiles**: Manage user profile information
- **Responsive Design**: Mobile-friendly interface

## Tech Stack

- **Backend**: Flask 3.1.3
- **Database**: SQLite
- **Frontend**: HTML, CSS, JavaScript
- **Testing**: pytest, pytest-flask
- **Python Version**: 3.8+

## Prerequisites

Before you begin, ensure you have:
- Python 3.8 or higher installed
- pip (Python package manager)
- Git

## Installation

1. **Clone the repository**
   ```bash
   git clone https://github.com/riteshkushwaha/money_expense_tracker.git
   cd money_expense_tracker
   ```

2. **Create a virtual environment** (optional but recommended)
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install dependencies**
   ```bash
   pip install -r requirements.txt
   ```

## Project Structure

```
expense-tracker/
├── app.py                 # Main Flask application
├── database/
│   ├── __init__.py
│   └── db.py             # Database initialization and utilities
├── static/
│   ├── css/
│   │   └── style.css     # Application styles
│   └── js/
│       └── main.js       # Client-side JavaScript
├── templates/
│   ├── base.html         # Base template
│   ├── landing.html      # Landing page
│   ├── login.html        # Login page
│   └── register.html     # Registration page
├── requirements.txt      # Python dependencies
└── README.md            # This file
```

## Getting Started

1. **Initialize the database**
   ```bash
   python3 -c "from database.db import init_db; init_db()"
   ```

2. **Run the application**
   ```bash
   python3 app.py
   ```

3. **Access the application**
   Open your browser and navigate to `http://localhost:5001`

## API Routes

### Authentication
- `GET /` - Landing page
- `GET /register` - Registration page
- `POST /register` - Register a new user
- `GET /login` - Login page
- `POST /login` - Authenticate user
- `GET /logout` - Logout user
- `GET /profile` - User profile page

### Expenses
- `GET /expenses/add` - Add expense form
- `POST /expenses/add` - Create new expense
- `GET /expenses/<id>/edit` - Edit expense form
- `POST /expenses/<id>/edit` - Update expense
- `GET /expenses/<id>/delete` - Delete expense

## Development

### Running Tests

```bash
pytest
```

### Debug Mode

The application runs in debug mode by default when started with `python3 app.py`, allowing for automatic reloading and detailed error messages.

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License

This project is open source and available under the MIT License. See LICENSE file for details.

## Author

[Ritesh Kushwaha](https://github.com/riteshkushwaha)

## Support

If you encounter any issues, please open an issue on [GitHub Issues](https://github.com/riteshkushwaha/money_expense_tracker/issues).
