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