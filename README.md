🚀 **Beginner CI/CD Project (End-to-End)**

🔥 **Project: Deploy a Simple Web App using CI/CD**
        Built an end-to-end CI/CD pipeline using Jenkins, Docker, and AWS EC2 to automate build and deployment of a Flask application with GitHub webhook integration.

🧩 Tools Used

      *Git & GitHub
      
      *Jenkins
      
      *Docker
      
      *AWS EC2

👉 Flow:

Developer pushes code → GitHub

        ↓
Jenkins builds project

        ↓
Docker image created

        ↓
Deploy to EC2 server

        ↓
Application live 🌐

step 1: **Create simple Python app and Docker File**

*app.py

*Docker file

Step 2: **Launch EC2 Instance**

Install Docker:
```
sudo apt update

sudo apt install docker.io -y

sudo systemctl start docker

sudo usermod -aG docker ubuntu
```


Step 3: **Edit Secuity Groups inbound rules**

Allow port: 8080
Allow port: 80

Step 4: **Install Jenkins on EC2**

👉 Access Jenkins:

http://<EC2-IP>:8080

Step 5: **Connect GitHub Repo**

Push project to GitHub

In Jenkins:
New Item → Freestyle Project
Source Code Management → Git → Paste repo URL

Step 6: **Add Build Steps in Jenkins**
```
docker build -t myapp .

docker stop myapp-container || true

docker rm myapp-container || true

docker run -d -p 80:80 --name myapp-container myapp
```
Step 7: **Enable Auto Trigger (CI)**

👉 In Jenkins:
Enable GitHub Webhook trigger

👉 In GitHub:

Settings → Webhooks

Add:

http://<EC2-IP>:8080/github-webhook/

Step 8: **Final Output**

✔ Push code → Automatically deployed
✔ App runs on:

http://<EC2-Public-IP>

<img width="1366" height="768" alt="ci-cd-01" src="https://github.com/user-attachments/assets/98ba4a9f-1cc4-4ad1-b0ad-a81f26189279" />
