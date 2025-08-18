**Docker Networking Basics**
- **Purpose**: Lets containers communicate with each other and the outside world;
- **Key Commands**:
    - `docker network ls` → List networks.
    - `docker network create` → Create a new network.
    - `docker network connect` → Attach a container to a network.    
- **Network Types**:
    1. **Bridge** (default) → Containers on the same host talk via private network (isolated from host).
    2. **Host** → Container shares host’s network directly (no isolation).
    3. **None** → No networking at all (fully isolated).
        
- **Why it matters**: Enables scalable, secure communication between containerized services.

CONNECTING CONTAINERS TOGETHER
**Goal**: Link a Flask application container with a MySQL database container using Docker’s networking so they can communicate via container names.

code 
# app.py

from flask import Flask
import MySQLdb

app = Flask(__name__)

@app.route('/')
def who_am_i():
    # Connect to the MySQL database
    db = MySQLdb.connect(
        host="mydb",    # Hostname of the MySQL container
       user="root",    # Username to connect to MySQL
        passwd="my-secret-pw",  # Password for the MySQL user
        db="mysql"      # Name of the database to connect to
    )

    cur = db.cursor()
    cur.execute("SELECT VERSION()")
    version = cur.fetchone()
    return f'I am a genius! MySQL version: {version[0]}'

if __name__ == '__main__':
    app.run(host='0.0.0.0', port=5000)


Note:
dockers networking feature allows containers to communicate via container names instead of IP Addresses.