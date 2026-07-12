# Docker Hands-on

## Environment

- OS: Windows 11 Home
- Virtualization: Intel VT-x Enabled
- WSL Version: WSL2
- Default Distribution: Ubuntu
- Docker Backend: WSL2
- Docker Desktop Installed

---

# Verify WSL

```bash
wsl --status
```

Output:

```
Default Distribution: Ubuntu
Default Version: 2
```

---

# Verify Docker Installation

```bash
docker version
```

Verify:
- Docker Client
- Docker Server
- Docker Engine Running

---

# Verify Docker Backend

```bash
wsl -l -v
```

Output:

```
Ubuntu              Stopped      2
docker-desktop      Running      2
```

This confirms Docker Desktop is using the WSL2 backend.

---

# Download Flowise Image

```bash
docker pull flowiseai/flowise
```

Verify:

```bash
docker images
```

---

# Create First Flowise Container

```bash
docker run -d --name flowise -p 3000:3000 flowiseai/flowise
```

Verify:

```bash
docker ps
```

Open:

```
http://localhost:3000
```

---

# Remove First Container

```bash
docker stop flowise

docker rm flowise
```

Verify:

```bash
docker ps -a
```

---

# Create Docker Volume

```bash
docker volume create flowise_data
```

Verify:

```bash
docker volume ls

docker volume inspect flowise_data
```

---

# Create Flowise Container with Persistent Storage

```bash
docker run -d \
--name flowise \
-p 3000:3000 \
-v flowise_data:/root/.flowise \
flowiseai/flowise
```

Verify:

```bash
docker ps

docker inspect flowise
```

Important Verification:

```
Source:
/var/lib/docker/volumes/flowise_data/_data

Destination:
/root/.flowise
```

---

# Open Flowise

```
http://localhost:3000
```

Create Administrator Account.

---

# Stop Flowise

```bash
docker stop flowise
```

---

# Start Flowise

```bash
docker start flowise
```

Verify:

```bash
docker ps
```

Open:

```
http://localhost:3000
```

---

# Stop Docker Desktop

Quit Docker Desktop from the System Tray.

---

# Start Docker Desktop

Open Docker Desktop.

Verify:

```bash
docker version
```

---

# Complete Architecture

```
Hardware
      ↓
Intel VT-x
      ↓
Microsoft Hypervisor
      ↓
WSL2
      ↓
docker-desktop
      ↓
Docker Engine
      ↓
Flowise Container
      ↓
Docker Volume
      ↓
Persistent Data
```

---

# Learnings

- Installed Docker Desktop using WSL2 backend.
- Verified Docker Engine.
- Downloaded Flowise Image.
- Created Flowise Container.
- Created Docker Volume.
- Attached Docker Volume to Flowise.
- Verified persistent storage.
- Verified container lifecycle.
- Verified Docker restart workflow.
- Understood Image → Container → Volume relationship.