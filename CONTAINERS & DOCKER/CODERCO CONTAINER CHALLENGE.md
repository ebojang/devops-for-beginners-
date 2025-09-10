## Requirements

1. **Flask Web Application**:
    - A Flask app that has two routes:
        - `/`: Displays a welcome message.
        - `/count`: Increments and displays a visit count stored in Redis.
2. **Redis Database**:
    - Use Redis as a key-value store to keep track of the visit count.
3. **Dockerize Both Services**:
    - Create Dockerfiles for both the Flask app and Redis.
    - Use Docker Compose to manage the multi-container application.
 
 ==MY APP.PY== 
from flask import Flask
import redis

app = Flask(__name__)
r = redis.Redis(host='redis', port=6379, db=0)

@app.route('/')
def home():
    return "coderco container challenge! Keep grinding "

@app.route('/count')
def count():
     visits = r.incr('visits')  # increment 'visits' in Redis
     return f'This page has been visited: {visits} times'

if  __name__ == '__main__':
    app.run(host='0.0.0.0', port=5002)

**LINE BY LINE BREAKDOWN** 
==Imports==
from flask import Flask
* We bring in Flask from the flask package: a pyhton framework. this help us build a small web server with routes (URLs).
import redis
* imports the Redis Client Library. 
* it allows our app to connect to Redis and run commands like set, get or incr .
==Flask app setup==
app = Flask(__name__)
* think of this as the "main controller" of our website. This is used to define the routes (URLs like / and /count).*
==Redis Connection==
r = redis.Redis(host='redis', port=6379, db=0)
* this creates a connection to Redis:*
* host='redis'` → The hostname of the Redis container. In Docker Compose, the service name is `redis`, so Flask can reach it.    
* port=6379` → Default port where Redis listens.    
* db=0` → Redis can have multiple databases (numbered 0, 1, 2…), we’re using the first one.
Now, `r` is our Redis client we’ll use in the routes.

==Homepage Route==
`@app.route('/') 
def home(): 
	return "coderco container challenge! Keep grinding "`

- `@app.route('/')` → This tells Flask: “When someone visits `/` (the root URL), run the function below.”
- `home()` → The function that executes when `/` is called.
- `return "coderco container challenge! Keep grinding "` → This is the response sent back to the user’s browser.

==Counter Route==
@app.route('/count')
def count():
     visits = r.incr('visits')  # increment 'visits' in Redis
     return f'This page has been visited: {visits} times' 
*- @app.route('/count')` → Defines a second route at `/count`.
- `r.incr('visits')` →
* incr` = increment a number in Redis.    
- If `visits` key doesn’t exist, Redis creates it and starts at `1`.    
*  Each time you refresh `/count`, Redis increases the value by 1.
So Redis is being used as a **persistent counter**.

 ==Running the App==

- `if __name__ == '__main__':` → This makes sure the app only runs if you execute `python app.py` directly (and not if it’s imported by another script).
- `app.run(host='0.0.0.0', port=5002)` →
    - `host='0.0.0.0'` → Makes the app accessible from any IP (needed for Docker).
    - `port=5002` → Flask listens on port **5002** inside the container.