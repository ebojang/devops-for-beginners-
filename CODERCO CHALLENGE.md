Create a multi-container application that consists of a simple Python Flask web application and a Redis database. The Flask application should use Redis to store and retrieve data.

## Requirements

[](https://github.com/CoderCo-Learning/containers-intro/tree/main/challenge#requirements)

1. **Flask Web Application**:
    
    - A Flask app that has two routes:
        - `/`: Displays a welcome message.
        - `/count`: Increments and displays a visit count stored in Redis.
2. **Redis Database**:
    
    - Use Redis as a key-value store to keep track of the visit count.
3. **Dockerize Both Services**:
    
    - Create Dockerfiles for both the Flask app and Redis.
    - Use Docker Compose to manage the multi-container application.


FIRST STEP:
Create flask application:
- **Flask**: A lightweight Python web framework to handle HTTP requests.
- **Redis**: An in-memory key-value database, perfect for fast, simple data like counters.
