# Cafe Website Album

This is a simple Flask web application for managing a database of cafes, built with SQLAlchemy, Flask-Bootstrap, and a SQLite database. It displays a list of cafes and their details sorted by name.

## Features
- Displays a list of cafes with their details.
- Uses SQLAlchemy ORM for database management.
- Data is stored in a SQLite database.
- Environment variables are used to secure sensitive data.

## Prerequisites
Before running this project, ensure you have the following installed:
- Python 3.9+
- pip (Python package manager)
- Virtual environment (optional but recommended)

## Installation and Setup

1. **Clone the Repository**
   ```bash
   git clone <repository-url>
   cd <repository-folder>
   ```

2. **Create and Activate a Virtual Environment** (optional but recommended)
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install Required Python Packages**
   ```bash
   pip install -r requirements.txt
   ```

4. **Set Up Environment Variables**
   Create a `.env` file in the project root and define the following variables:
   ```env
   FLASK_KEY=your_secret_key_here
   CAFE_DB_URI=sqlite:///cafe.db
   ```

5. **Run the Application**
   ```bash
   python app.py
   ```
   The application will run on `http://127.0.0.1:5000/` by default.

## File Structure
```plaintext
.
├── app.py                # Main Flask application file
├── templates/
│   └── index.html        # HTML template for rendering the cafes
├── .env                  # Environment variables file (not tracked by Git)
├── requirements.txt      # List of Python dependencies
└── README.md             # Project documentation
```

## Key Components

### `app.py`
- Initializes the Flask app with a secret key.
- Configures SQLAlchemy for managing the SQLite database.
- Defines the `Cafes` model with the following columns:
  - `id`: Primary key (integer, unique, auto-incremented).
  - `name`: Name of the cafe (string, unique, non-nullable).
  - `map_url`: Google Maps link (string, non-nullable).
  - `img_url`: Image URL of the cafe (string, non-nullable).
  - `rating`: Rating of the cafe (float, non-nullable).
  - `price`: Price level (string, non-nullable).
  - `location`: Location of the cafe (string, non-nullable).
- Creates the database tables when the app starts.
- Provides a route (`/`) for displaying all cafes.

### Templates
- `index.html`: Displays the list of cafes dynamically.

## Adding Cafes to the Database
You can add cafes to the `cafe_db` table manually using a database management tool such as [DB Browser for SQLite](https://sqlitebrowser.org/) or programmatically with SQLAlchemy.

Example SQL:
```sql
INSERT INTO cafe_db (name, map_url, img_url, rating, price, location)
VALUES ('Cafe Example', 'https://maps.example.com', 'https://img.example.com', 4.5, '$$', 'Example Location');
```

## Dependencies
The project relies on the following Python packages:
- `Flask`: Web framework
- `Flask-Bootstrap`: Front-end integration
- `Flask-SQLAlchemy`: SQLAlchemy ORM integration
- `SQLAlchemy`: ORM for database interaction
- `python-dotenv`: For loading environment variables

Install these dependencies using:
```bash
pip install Flask Flask-Bootstrap Flask-SQLAlchemy python-dotenv
```

## Contact
If you have any questions or suggestions, feel free to reach out!

