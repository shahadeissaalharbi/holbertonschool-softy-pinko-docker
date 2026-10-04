# Softy Pinko Docker

A Docker project that builds a small web infrastructure: a reverse proxy,
a load balancer, two API servers, and a static front-end server.

## Architecture

- **Proxy (Nginx)**: single entry point on port 80. Routes `/` to the
  front-end and `/api` to the back-end, load-balancing API requests
  using Round Robin.
- **Front-end (Nginx)**: serves the static Softy Pinko site on port 9000
  (internal only).
- **Back-end (Flask)**: API server on port 5252 (internal only) with the
  endpoint `/api/hello`.

## Tasks

| Task | Description |
|------|-------------|
| task0 | First Dockerfile (Ubuntu, apt update/upgrade) |
| task1 | Back-end: Flask API in Docker |
| task2 | Front-end: Nginx static server |
| task3 | Connecting front-end and back-end (CORS) |
| task4 | Docker Compose |
| task5 | Proxy server (Nginx reverse proxy) |
| task6 | Horizontal scaling with 2 API servers |

## Usage

Requires Docker Desktop.

```bash
cd task6
docker-compose up --scale back-end=2
```

Then open `http://localhost`.

## Author

Shahad Eissa Alharbi
