# Docker Fundamentals

## What is Docker?

Docker is an open-source containerization platform that allows developers to package an application along with all its dependencies into a lightweight, portable unit called a **Container**.

This ensures the application behaves the same across Development, Testing, Staging, and Production environments.

---

## Why Docker?

- Eliminates "Works on My Machine" issues.
- Provides consistent environments across all stages.
- Lightweight compared to Virtual Machines.
- Faster application deployment.
- Easy scalability.
- Simplifies application distribution.
- Supports microservices architecture.

---

## Key Components

### Docker Engine

Docker Engine is the core runtime responsible for creating, running, stopping, and managing Docker Containers.

---

### Docker Image

A Docker Image is a **read-only blueprint/template** used to create one or more containers.

Example:

```
Flowise Image
      ↓
Creates
      ↓
Flowise Container
```

Think of it as:

```
Java Class
      ↓
Creates
      ↓
Object
```

---

### Docker Container

A Docker Container is a **running instance of a Docker Image**.

One Image can create multiple Containers.

Example:

```
Flowise Image
      ├── Flowise Container 1
      ├── Flowise Container 2
      └── Flowise Container 3
```

---

### Docker Volume

A Docker Volume provides **persistent storage** outside the container.

Purpose:

- Store application data
- Data remains even if the container is deleted
- Can be attached to new containers

Example:

```
Flowise Container
        ↓
Reads/Writes
        ↓
Docker Volume
        ↓
Chatflows
Agentflows
Credentials
Settings
```

---

## Image vs Container

| Docker Image | Docker Container |
|---------------|------------------|
| Blueprint / Template | Running Instance |
| Read Only | Read & Write |
| Can create multiple containers | Created from one image |
| Stored locally | Runs using Docker Engine |

---

## Container Lifecycle

```
Docker Hub
      ↓
docker pull
      ↓
Image
      ↓
docker run
      ↓
Container Created
      ↓
Container Running
      ↓
docker stop
      ↓
Container Stopped
      ↓
docker start
      ↓
Container Running
      ↓
docker rm
      ↓
Container Deleted
```

---

## Docker Volume Lifecycle

```
Create Volume
      ↓
Attach Volume to Container
      ↓
Application Stores Data
      ↓
Delete Container
      ↓
Volume Still Exists
      ↓
Create New Container
      ↓
Attach Same Volume
      ↓
Old Data Restored
```

---

## Flowise Installation Flow

```
Docker Hub
      ↓
docker pull flowiseai/flowise
      ↓
Flowise Image
      ↓
docker run
      ↓
Flowise Container
      ↓
Open Browser
      ↓
http://localhost:3000
```

---

## Docker on Windows (WSL2)

```
Hardware
      ↓
Intel VT-x / AMD-V
      ↓
Microsoft Hypervisor
      ↓
WSL2
      ↓
docker-desktop
      ↓
Docker Engine
      ↓
Docker Container
```

---

## Docker + Flowise Architecture

```
Windows 11
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

## Important Points

- Docker Image is a blueprint.
- Docker Container is a running instance of an Image.
- One Image can create multiple Containers.
- Docker Volumes provide persistent storage.
- Deleting a Container does not delete the Volume.
- Docker Desktop on Windows uses the WSL2 backend.
- Docker Engine runs inside the `docker-desktop` WSL distribution.
- Flowise data is stored in the Docker Volume, not inside the Container.