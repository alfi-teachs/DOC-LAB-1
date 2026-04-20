# DOC-LAB-1

# Step 1: Launch EC2 (Amazon Linux) & Connect   
```bash 
Sudo su
```

# Step 2: Update System

```bash 
yum update -y
```
# Step 3: Install Docker
```bash 
sudo yum install docker -y

```
# Step 4: Check Docker Version
```bash 
docker --version

```
# Step 5: Start Docker
```bash 
sudo systemctl start docker

```
# Step 6: Check Docker Status
```bash 
sudo systemctl status docker

```
# Step 7: Switch to Root (optional)
```bash 
sudo su

```
# Step 8: Check Images
```bash 
docker images
```

# Step 9: Create Dockerfile
```bash

nano Dockerfile
```

Paste
FROM nginx
COPY . /usr/share/nginx/html
Save and exit:   CTRL + X → Y → Enter
# Step 10: Build Image
```bash
docker build -t testapp .

```                                                                                                                                                       
# Step 11: Create Repository in Docker Hub

 Go to Docker Hub
Click Create Repository
Enter:
Repository Name: testapp
Description: (any)
Visibility: Public or Private
Click Create
# Step 12: Generate Access Token
Go to Profile → Account Settings
In the left sidebar,
Click personal  Access Token
Enter:
Description: my-token
Expiry: choose any
Permissions: Read, Write, Delete
Click Generate
Copy the token
# Step 13: Login to Docker Hub
docker login
👉 Enter:
Username: your username
Password: paste access token
# Step 14: Tag Image (Important)
```bash
docker tag <old-image-name> <username>/testapp:v1

```
Example:
docker tag testapp alfia123/testapp:v1

# step 15 Push Image
👉 Image name must match your Docker Hub repository
```bash 
docker push <username>/testapp:v1
```
Example:  docker push alfia123/testapp:v1

# Step 16: Verify
Go to Docker Hub
Open your repository testapp
You will see image with tag v1

# Quick Flow
Create EC2 → Install Docker → Build Image → Create Repo → Login → Tag → Push → Verify
