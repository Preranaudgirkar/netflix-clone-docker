# netflix-clone-docker
# StreamFlix - Netflix Clone (Dockerized Static Website)

A Netflix-inspired static website served inside a Docker container using Nginx.
Built for learning Docker, containerization, and static web deployment.

---

## Tech Stack

| Technology | Purpose |
|------------|---------|
| HTML5 / CSS3 / JavaScript | Frontend UI |
| Docker | Containerization |
| Nginx | Static file server inside container |

---

## Project Structure
netflix-clone-docker/
|
|-- index.html        # Main StreamFlix UI
|-- Dockerfile        # Docker image configuration
|-- README.md         # Project documentation

---

## Dockerfile

```dockerfile
FROM nginx:alpine

RUN rm -rf /usr/share/nginx/html/*

COPY index.html /usr/share/nginx/html/index.html

EXPOSE 80

CMD ["nginx", "-g", "daemon off;"]
```

---

## How to Run with Docker

### Step 1 - Build the Docker image

```bash
docker build -t streamflix .
```

### Step 2 - Run the container

```bash
docker run -d -p 8080:80 --name streamflix-app streamflix
```

### Step 3 - Open in browser
http://localhost:8080
