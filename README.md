# kubernetes----77-
# Kubernetes (K8S)
- It is an open source container orchestration platform that automates many of the manual processes involved in deploying, managing, and scaling containerized applications.
-  It was originally developed by Google and is now maintained by the Cloud Native Computing Foundation.


# ![image](https://github.com/user-attachments/assets/2324a0f7-0072-42f3-a614-b5b984bfcabf)


**Key features of Kubernetes include**:
1. Container Management: Simplifies running and managing containers across clusters.
2. Scaling: Automatically adjusts the number of active containers based on demand.
3. Load Balancing: Distributes traffic to ensure no single container is overwhelmed.
4. Self-healing: Automatically restarts failed containers and replaces or reschedules them as needed.
5. Service Discovery: Allows containers to communicate with each other and external services seamlessly.
6. Configuration Management: Manages application configuration and secrets securely.

# Kubernetes cluster
- A working Kubernetes deployment is called a cluster, which is a group of hosts running Linux containers. You can visualize a Kubernetes cluster as two parts: the control plane and the compute machines, or nodes.

- Each node is its own Linux environment, and could be either a physical or virtual machine. Each node runs pods, which are made up of containers.

# Kubernetes vs Docker
- Docker can be used as a container runtime that Kubernetes orchestrates. When Kubernetes schedules a pod to a node, the kubelet (the service that makes sure each container is running) on that node will instruct Docker to launch the specified containers.
- The difference when using Kubernetes with Docker is that an automated system asks Docker to do those things instead of the admin doing so manually on all nodes for all containers.

# ![image](https://github.com/user-attachments/assets/3e873b57-b536-44d0-8406-1f00faf3bbc1)

# Minikube
![image](https://github.com/user-attachments/assets/d13159ed-cc18-4267-b491-4323cb9ec9c6)

- Minikube is a one-node Kubernetes cluster where master processes and work processes both run on one node.
- Minikube is local Kubernetes, focusing on making it easy to learn and develop for Kubernetes.

# Benefits of Minikube
1. Ease of Installation and Setup
2. Cost-Effective Learning Environment
3. Fast Development Cycle
4. Experimentation Without Risk
5. Portable Environment

# How to install Minikube ?
**Step 1: Open PuTTY**          
 - Enter the Hostname or IP Address.       
 - Click Open.      
 - Login to the server by writing ubuntu.       

2. **STEP 2:** Install docker using the following command

           curl -sL https://github.com/ShubhamTatvamasi/docker-install/raw/master/docker-install.sh | bash

![WhatsApp Image 2024-09-23 at 15 13 50_890bcc7a](https://github.com/user-attachments/assets/6a62086d-595f-4ea4-abae-109fdb571018)


4. **STEP 3:**  Add your local user to docker group so that your local user run docker commands without sudo.

               sudo usermod -aG docker $USER

5. **STEP 4:** Now enter the following command

              $ newgrp docker

6. **STEP 5:** Install the Kubernetes command-line tool, kubectl, via the Snap package management system

               sudo snap install kubectl --classic

               kubectl version --client

7. **STEP 6:** Download and Install Minikube Binary

                curl -LO https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64

                sudo install minikube-linux-amd64 /usr/local/bin/minikube

8. **STEP 7:** Verify minikube version by following command

                minikube version

![WhatsApp Image 2024-09-23 at 15 13 52_d790956c](https://github.com/user-attachments/assets/5da6aaac-b513-44c0-b895-9fffe50c0fb8)

9. **STEP 8:** Install Kubectl tool

                curl -LO https://storage.googleapis.com/kubernetes-release/release/`curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt`/bin/linux/amd64/kubectl

10. **STEP 9:** Start Minikube Cluster

                minikube start --driver=docker

11. **STEP 10:** Verify the status of your cluster

                minikube status

![WhatsApp Image 2024-09-24 at 00 39 14_7cfa6cbf](https://github.com/user-attachments/assets/104cb600-c576-42b9-812a-60a979c43e71)

12. **STEP 11** Grant permissions

                kubectl cluster-info

                Kubectl config view

                kubectl get nodes

                kubectl get pods

13. **STEP 12** start the Kubernetes dashboard run below command

                minikube dashboard
               
 kubectl proxy --address='0.0.0.0' --disable-filter=true &

15. **STEP 13** Use the following url on browser and use your public ip 

               http://public_ip:8001/api/v1/namespaces/kubernetes-dashboard/services/http:kubernetes-dashboard:/proxy/

![image alt](https://www.linuxbuzz.com/wp-content/uploads/2023/11/Kubernetes-Dashboard-GUI-Minikube-Ubuntu-1024x640.png)
