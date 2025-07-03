# Odoo Volume: Docker Installation & Usage Guide

This guide will help you install Docker on different operating systems and run the Odoo stack using Docker Compose.

## 1. Install Docker

### macOS
1. Download Docker Desktop for Mac from [Docker Hub](https://www.docker.com/products/docker-desktop/).
2. Open the downloaded `.dmg` file and drag Docker to Applications.
3. Launch Docker from Applications and follow the setup instructions.

### Windows
1. Download Docker Desktop for Windows from [Docker Hub](https://www.docker.com/products/docker-desktop/).
2. Run the installer and follow the setup instructions.
3. After installation, launch Docker Desktop.

### Linux (Ubuntu example)
1. Update your package index:
   ```sh
   sudo apt-get update
   ```
2. Install Docker:
   ```sh
   sudo apt-get install docker.io
   ```
3. Start Docker and enable it to run on boot:
   ```sh
   sudo systemctl start docker
   sudo systemctl enable docker
   ```
4. (Optional) Add your user to the `docker` group:
   ```sh
   sudo usermod -aG docker $USER
   # Log out and log back in for this to take effect
   ```

### Verify Docker Installation
Run:
```sh
docker --version
```
You should see the installed Docker version.

## 2. Install Docker Compose

- **Docker Desktop (macOS/Windows)**: Docker Compose is included.
- **Linux**: Install Docker Compose plugin:
  ```sh
  sudo apt-get install docker-compose-plugin
  ```
  Or, for the standalone version, see [Docker Compose Install Docs](https://docs.docker.com/compose/install/).

Verify with:
```sh
docker compose version
```

## 3. Running the Odoo Stack

1. Open a terminal and navigate to the project directory:
   ```sh
   cd /path/to/odoo-volume
   ```
2. Start the services:
   ```sh
   docker compose up
   ```
   - Add `-d` to run in detached mode: `docker compose up -d`

3. Access Odoo in your browser at: [http://localhost:8069](http://localhost:8069)

## 4. Stopping the Stack
To stop the services, press `Ctrl+C` or run:
```sh
docker compose down
```

## 5. Troubleshooting
- Ensure Docker is running before executing Docker Compose commands.
- For permission issues on Linux, ensure your user is in the `docker` group.
- Check logs with:
  ```sh
  docker compose logs
  ```

---
For more details, see the [official Docker documentation](https://docs.docker.com/).
