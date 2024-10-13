Task Management API
This project is a Django-based Task Management API that allows users to create, manage, and track tasks. It includes JWT authentication, task filtering, sorting, and pagination.

Features:
JWT-based authentication (user registration and login)
Task creation, updating, deletion, and retrieval
Task filtering by status and priority
Task sorting by due date, priority, or creation date
Pagination for task lists
API documentation  Postman Collection


Project Setup:
Step 1: Clone the Repository
git clone https://github.com/sushantkrjha/task-management-api.git
cd task-management-api

Step 2: Create a Virtual Environment and Activate It
python -m venv venv
source venv/bin/activate 

Step 3: Install Dependencies
pip install -r requirements.txt

Step 4: Apply Migrations
python manage.py migrate

Step 5: Run the Server
python manage.py runserver

Authentication
The project uses JSON Web Tokens (JWT) for authentication. Users must register and log in to get a token.

User Registration
Endpoint: /auth/register/
Method: POST
Request Body:

{
    "username": "example_user",
    "password": "example_password"
}
User Login
Endpoint: /auth/login/
Method: POST

Request Body:

{
    "username": "example_user",
    "password": "example_password"
}
Response:

{
    "token": "JWT-TOKEN"
}


Task Management API Endpoints
1. Create a Task

Endpoint: /tasks/
Method: POST
Request Body:

{
    "title": "New Task",
    "description": "Task description",
    "status": "pending",
    "priority": "medium",
    "due_date": "2024-12-01"
}

2. Retrieve All Tasks

Endpoint: /tasks/
Method: GET
Optional Query Parameters:
Filter by status: /tasks/?status=pending
Filter by priority: /tasks/?priority=high
Sort by due date: /tasks/?ordering=due_date
Sort by priority (descending): /tasks/?ordering=-priority


3. Retrieve a Single Task

Endpoint: /tasks/{task_id}/
Method: GET


4. Update a Task

Endpoint: /tasks/{task_id}/
Method: PUT or PATCH
Request Body:

{
    "title": "Updated Task",
    "status": "in-progress",
    "priority": "high"
}


5. Delete a Task

Endpoint: /tasks/{task_id}/
Method: DELETE
Pagination, Filtering, and Sorting


Pagination: Each page contains 10 tasks. The next and previous pages can be accessed via links in the response.

Filtering: You can filter tasks by status and priority.
Sorting: Tasks can be sorted by due_date, priority, or created_at in ascending or descending order.


Extra Assumptions and Improvements:

Implemented JWT authentication to ensure users can only manage their own tasks.
Added pagination to make task retrieval efficient.
Sorting and filtering were added to enhance user experience when working with task lists.
DjangoFilterBackend and OrderingFilter were used to simplify filtering and sorting logic.




