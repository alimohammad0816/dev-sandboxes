# dev-sandboxes
🚀 Ready-to-use Docker-based development sandboxes with SSH access

## Usage

### Method 1
```bash
docker compose up -d --build
```

### Method 2
#### 1 - Build Image
```bash
docker build -t dev-sandbox-ubuntu24 -f YOUR_DOCKER .
```
#### 2 - Run
```bash
docker run -d --name {{YOUR_SAND_BOX_NAME}} -p {{YOUR_LOCAL_PORT}}:22 dev-sandbox-ubuntu24
```
#### 3 - add ssh key
```bash
docker cp ~/.ssh/id_rsa.pub {{YOUR_SAND_BOX_NAME}}:/home/developer/.ssh/authorized_keys
docker exec -it sandbox22 chown developer:developer /home/developer/.ssh/authorized_keys
docker exec -it sandbox22 chmod 600 /home/developer/.ssh/authorized_keys
```
