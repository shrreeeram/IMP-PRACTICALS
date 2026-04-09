Install & Start Docker Desktop
Steps:
1.	Install + Open Docker Desktop 
2.	Wait till it shows → “Docker is running” ✔ 
Check:
docker --version
docker ps
________________________________________
Login to Microsoft Azure Portal
https://portal.azure.com
✔ Login hona chahiye
________________________________________
⚙️ Install Jenkins (for CI/CD)
•	Install ya already lab me hoga













1.	List running containers and stopped containers using Docker CLI.
Steps:
1.	CMD open 
2.	Run: 
docker ps
👉 Running containers
3.	Run: 
docker ps -a
👉 All containers
Viva line:
“docker ps shows running, docker ps -a shows all containers”

 
2.	Create and run a Docker container using the Nginx image and access it through the browser.
2. Run Nginx container & access browser
Steps:
1.	Run: 
docker run -d -p 8080:80 nginx
2.	Browser open →
👉 http://localhost:8080 
Explanation:
•	-d → background 
•	-p → port mapping
 
3.	Configure Role-Based Access Control (RBAC) for an Azure resource group.
Steps:
1.	Azure Portal open 
2.	Resource Group open 
3.	Click Access Control (IAM) 
4.	Click Add → Role Assignment 
5.	Select Role: 
o	Owner / Contributor / Reader 
6.	Select user 
7.	Click Save 
Viva line:
“RBAC controls who can access Azure resources based on roles”

 
4.	Pull an Ubuntu Docker image from Docker Hub and run it as a container.
Steps:
docker pull ubuntu
docker run -it ubuntu
👉 Container ke andar aa jaoge
Exit:
exit 
5.	Create a Kubernetes Pod using a Nginx container image.
Requirement:
👉 Docker Desktop → Enable Kubernetes
Steps:
1.	Create file: pod.yaml 
apiVersion: v1
kind: Pod
metadata:
  name: nginx-pod
spec:
  containers:
  - name: nginx
    image: nginx
2.	Run: 
kubectl apply -f pod.yaml
kubectl get pods
 
6.	Deploy a Kubernetes Deployment with 3 replicas of a containerized application.
Steps:
kubectl create deployment myapp --image=nginx --replicas=3
kubectl get deployments
Steps:
1.	Azure Portal 
2.	Search Virtual Machines 
3.	Click Create 
4.	Fill: 
o	OS → Ubuntu 
o	Username/password 
5.	Click Create
 
6.	Create a Virtual Machine in Microsoft Azure using the Azure Portal.
Step 2:
•	Search bar me likho: Virtual Machines 
•	Click karo 
Step 3: Top pe Create → Azure Virtual Machine click karo 
Step 4: (Basic Tab)
Fill carefully:
•	Subscription → Default rehne do 
•	Resource Group → 
o	Agar nahi hai → “Create new” → naam likh do (ex: myRG) 
•	Virtual Machine Name → (ex: myVM) 
•	Region → India choose karo 
•	Image (OS) → Ubuntu select karo 
•	Size → Default (change mat karo) 
Step 5: (Administrator Account)
•	Username → (ex: shree) 
•	Password → strong password 
•	Confirm password 
Step 6: Inbound ports → Allow HTTP + SSH ✔ 
Step 7:
•	Click → Review + Create 
•	Then → Create 
⏳ 2–5 min wait
Step 8: Go to resource → VM ready ✔ 
Viva line:
“Virtual Machine is a virtual computer created in cloud using Azure”
8.	Create a Docker image for a simple web application and push it to Azure Container Registry (ACR).
Step 1: Create ACR in Azure
1.	Azure Portal → search Container Registry 
2.	Click Create 
Fill:
•	Resource Group → select 
•	Registry name → unique (ex: shreeacr123) 
•	Region → India 
•	SKU → Basic 
👉 Click Create
________________________________________
✅ Step 2: Login ACR (IMPORTANT)
az acr login --name shreeacr123
________________________________________
✅ Step 3: Build Docker Image
docker build -t myapp .
________________________________________
✅ Step 4: Tag Image
docker tag myapp shreeacr123.azurecr.io/myapp
________________________________________
✅ Step 5: Push Image
docker push shreeacr123.azurecr.io/myapp
________________________________________
Viva line:
“ACR is used to store and manage Docker images in Azure” 
9.	Create a CI/CD pipeline using Jenkins to automatically build and deploy Dockerized application.
Steps:
Step 1:
•	Open Jenkins (localhost:8080) 
Step 2:
•	Click New Item 
•	Name → myproject 
•	Select → Freestyle project 
Step 3:
•	Source Code → Git 
•	Paste GitHub repo link 
Step 4:
•	Scroll → Build section 
•	Add build step → Execute shell 
Paste:
docker build -t myapp .
Step 5:
•	Save 
Step 6:
•	Click → Build Now 
Viva line:
“CI/CD automates build and deployment using Jenkins”
 
10.	Enable Azure Monitor for a Virtual Machine.
Requirement:
•	VM already created ✔ 
________________________________________
✅ Steps:
1.	Azure Portal 
2.	Virtual Machine open 
3.	Left side → Monitoring 
4.	Click Insights 
5.	Click Enable 
________________________________________
Viva line:
“Azure Monitor is used to track performance and logs of VM”
 
11.	Demonstrate 5 Kubernetes commands.
Just write in cmd (Kubernetes enable)

kubectl get pods
kubectl get nodes
kubectl apply -f file.yaml
kubectl delete pod pod-name
kubectl describe pod pod-name 
12.	Demonstrate 5 docker commands.

docker ps
docker pull nginx
docker run nginx
docker stop container_id
docker rm container_id 
13.	 Create 1 Container using docker.
Steps:
docker run -it ubuntu
👉 Container start ho jayega
 
14.	Demonstrate port mapping for docker image.
Steps:
docker run -d -p 8080:80 nginx
👉 Browser:
http://localhost:8080
 
15.	Build a Docker image using the Docker file and run it as a container.
Dockerfile Build & Run
📌 Step 1: Create file → Dockerfile
FROM nginx
COPY . /usr/share/nginx/html
________________________________________
📌 Step 2: Build image
docker build -t myweb .
________________________________________
📌 Step 3: Run container
docker run -d -p 8080:80 myweb
________________________________________
Viva line:
“Dockerfile is used to create custom Docker images”

