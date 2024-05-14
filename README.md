# TODO list API

#### This is a REST API built using the FastAPI library to manage a list of to-do tasks stored in a MySQL database. The API uses authentication and only allows access to users with a valid API key.

## Features
- Create, retrieve, update, and delete to-do tasks.
- Uses authentication to ensure only authorized users can access the API.
- Connects to a MySQL database to store task information.

## Endpoints
- `GET /` Returns a welcome message for authorized users.
- `GET /tasks` Retrieve all tasks stored in the database.
- `POST /tasks` Add a new task to the database.
- `PUT /task/{task_id}` Update an existing task in the database.
- `DELETE /task/{task_id}` Update an existing task in the database.

## Requirements
- Python 3.6+
- Fast-API
- mysql-connector-python
- python-dotenv
- pydantic
- uvicorn

## Installation 
- Run the command below to install necessary modules.
    ```
    pip install fastapi mysql-connector-python pydantic python-dotenv uvicorn uvicorn[standard]
    ```

## Database Structure

    CREATE TABLE tasks (
    task_id INT AUTO_INCREMENT PRIMARY KEY,
    task VARCHAR(255) NOT NULL,
    done BOOLEAN NOT NULL DEFAULT FALSE
    );

    +---------+-----------------+------+
    | task_id | task            | done |
    +---------+-----------------+------+
    |         |                 |      |
    +---------+-----------------+------+


    CREATE TABLE api_keys (
    api_id INT AUTO_INCREMENT PRIMARY KEY,
    api_key VARCHAR(255) NOT NULL
    );
    
    +--------+---------+
    | api_id | api_key |
    +--------+---------+
    |        |         |
    +--------+---------+
    
## Usage
#### Note: Please make sure to have a MySQL database set up and the necessary environment variables defined before running the API.
- open terminal/command_prompt where project is installed.
- Run `uvicorn main:app --reload` command.
- Now it will be running in localhost at port 8000.
- Checkout at http://127.0.0.1:8000/docs?api_key=YOUR-TOKEN
