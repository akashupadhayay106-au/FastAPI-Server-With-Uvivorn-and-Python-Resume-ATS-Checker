# FastAPI Resume Checker

This project is a web application that allows users to upload resumes and check them. It uses FastAPI for the backend and a simple HTML, CSS, and JavaScript frontend.

## Tech Stack

**Backend:**
*   Python
*   FastAPI
*   Uvicorn
*   SQLAlchemy

**Frontend:**
*   HTML
*   CSS
*   JavaScript

## Installation

1.  **Clone the repository:**
    ```bash
    git clone <repository-url>
    cd <repository-folder>
    ```

2.  **Backend Setup:**
    *   Navigate to the `backend` directory:
        ```bash
        cd backend
        ```
    *   Create a virtual environment:
        ```bash
        python -m venv venv
        ```
    *   Activate the virtual environment:
        *   On Windows:
            ```bash
            venv\Scripts\activate
            ```
        *   On macOS/Linux:
            ```bash
            source venv/bin/activate
            ```
    *   Install the required packages:
        ```bash
        pip install -r requirements.txt
        ```
        *(Note: You may need to create a `requirements.txt` file first. See the "Creating requirements.txt" section below.)*

3.  **Creating `requirements.txt`:**
    If you don't have a `requirements.txt` file, you can create one with the following content:
    ```
    fastapi
    uvicorn
    sqlalchemy
    python-multipart
    ```
    Then run `pip install -r requirements.txt`.

## Running the Application

1.  **Start the backend server:**
    *   Make sure you are in the `backend` directory with the virtual environment activated.
    *   Run the following command:
        ```bash
        uvicorn main:app --reload
        ```
    *   The server will be running at `http://127.0.0.1:8000`.

2.  **Open the frontend:**
    *   Navigate to the `frontend` directory.
    *   Open the `index.html` file in your web browser.

## How It Works

1.  The user opens `index.html` to see the main page.
2.  They can navigate to the signup or login pages.
3.  After logging in, they are redirected to the dashboard.
4.  From the dashboard, they can upload a resume.
5.  The frontend sends the resume to the FastAPI backend.
6.  The backend processes the resume and returns the results.

## Project Structure

```
.
├── backend
│   ├── __pycache__
│   ├── venv
│   ├── config.py
│   ├── database.py
│   ├── main.py
│   ├── models.py
│   ├── requirements.txt
│   ├── schemas.py
│   └── user.py
├── frontend
│   ├── dashboard.html
│   ├── index.html
│   ├── login.html
│   ├── script.js
│   ├── signup.html
│   ├── style.css
│   └── upload.html
├── .gitignore
├── database.sql
├── dummy_resume.pdf
├── models.py
├── README.md
└── test.db
```

### Key Files

*   `backend/main.py`: The main FastAPI application file, containing the API endpoints.
*   `backend/database.py`: Handles database connection and session management.
*   `backend/models.py`: Defines the SQLAlchemy database models.
*   `backend/schemas.py`: Defines the Pydantic schemas for data validation.
*   `frontend/index.html`: The main landing page for the application.
*   `frontend/script.js`: Contains the JavaScript logic for the frontend.
*   `frontend/style.css`: Contains the CSS styles for the frontend.

## API Endpoints

The following are the main API endpoints available in the backend:

*   `POST /signup`: Creates a new user account.
*   `POST /login`: Authenticates a user and returns a token.
*   `POST /upload`: Uploads a resume for processing.
*   `GET /dashboard`: Retrieves user-specific dashboard data.

For a detailed list of all endpoints and their parameters, you can access the interactive API documentation provided by FastAPI at `http://127.0.0.1:8000/docs` when the server is running.

## Database Setup

The application uses a SQLite database (`test.db`) for simplicity. The database is automatically created when the application starts for the first time. The SQLAlchemy models in `backend/models.py` define the table structure.

If you need to reset the database, you can simply delete the `test.db` file, and it will be recreated on the next application run.
