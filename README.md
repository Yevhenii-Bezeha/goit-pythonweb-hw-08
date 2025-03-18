# FastAPI Contacts API

This is a simple REST API built with FastAPI and PostgreSQL to manage contacts. It supports CRUD operations and additional functionality like searching contacts and retrieving upcoming birthdays.

## Features
- Create a new contact
- Retrieve all contacts
- Retrieve a contact by ID
- Update a contact
- Delete a contact
- Search contacts by name or email
- Get contacts with upcoming birthdays (next 7 days)

## Technologies Used
- FastAPI
- SQLAlchemy
- PostgreSQL
- Pydantic
- Docker (optional for running PostgreSQL)

## Installation & Setup

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/fastapi-contacts-api.git
cd fastapi-contacts-api
```

### 2. Create a Virtual Environment
```bash
python3 -m venv venv
source venv/bin/activate  # On Windows use: venv\Scripts\activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

### 4. Setup PostgreSQL
If you don’t have PostgreSQL installed, you can run it using Docker:
```bash
docker run --name some-postgres -p 5432:5432 -e POSTGRES_PASSWORD=mysecretpassword -d postgres
```

### 5. Initialize the Database
```bash
python -c "from database import Base, engine; Base.metadata.create_all(bind=engine)"
```

### 6. Run the API
```bash
uvicorn main:app --reload
```

## API Endpoints
| Method  | Endpoint                         | Description |
|---------|----------------------------------|-------------|
| POST    | `/contacts/`                     | Create a new contact |
| GET     | `/contacts/`                     | Get all contacts (with optional search by name/email) |
| GET     | `/contacts/{contact_id}`         | Get a contact by ID |
| PUT     | `/contacts/{contact_id}`         | Update an existing contact |
| DELETE  | `/contacts/{contact_id}`         | Delete a contact |
| GET     | `/contacts/upcoming_birthdays/`  | Get contacts with birthdays in the next 7 days |

## Access API Documentation
Once the server is running, you can access interactive API documentation at:
- Swagger UI: [http://127.0.0.1:8000/docs](http://127.0.0.1:8000/docs)
- Redoc: [http://127.0.0.1:8000/redoc](http://127.0.0.1:8000/redoc)

## Contributing
Feel free to submit issues or pull requests to improve this project!

## License
This project is licensed under the MIT License.

