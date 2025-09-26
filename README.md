# FUTURE_CS_03

# Secure File Sharing System - Task 3

This project is a simple but secure file sharing web portal built with Python and Flask, as part of the Future Interns cybersecurity internship program. The application allows users to upload files, which are then encrypted using AES-256 before being stored on the server.

## Features
-   Secure file upload functionality.
-   **AES-256 Encryption:** All files are encrypted at rest to ensure confidentiality.
-   Simple and clean user interface.

## Technology Stack
-   **Backend:** Python 3, Flask
-   **Cryptography:** PyCryptodome (for AES encryption)
-   **Frontend:** HTML & CSS

## Setup and Usage
1.  **Clone the repository:**
    ```bash
    git clone <your-repo-url>
    cd secure-file-sharing
    ```
2.  **Create and activate a virtual environment:**
    ```bash
    python -m venv venv
    # On Windows
    .\venv\Scripts\activate
    # On macOS/Linux
    source venv/bin/activate
    ```
3.  **Install dependencies:**
    ```bash
    pip install -r requirements.txt
    ```
4.  **Run the application:**
    ```bash
    # On Windows
    $env:FLASK_APP = "app.py"
    flask run
    # On macOS/Linux
    export FLASK_APP=app.py
    flask run
    ```
5.  Open your browser and navigate to `http://127.0.0.1:5000`.
