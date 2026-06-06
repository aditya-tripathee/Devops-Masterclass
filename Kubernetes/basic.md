- Docker solved "it works on my machine" by packaging the dependencies and apps into containers.

# Orchestration
It means automatcially managing many containers across machines - including running , scaling , networking and healing them.

# Why we need orchestration ?
- We need orchestration because managing a small number of containers (like 5–6) can be done manually, but in real-world applications we often have hundreds of containers. It becomes very difficult to monitor, restart, scale, and distribute traffic manually.

- Orchestration tools (like Kubernetes) automate this process by handling container deployment, scaling, load balancing, and self-healing, ensuring the system runs efficiently and reliably.

# Kubernetes
- A conatiner orchestration platform that manages conatiners for you at scale.
- It automates deployment, scaling , healing , networking and management of containerized applications.

# Docker
- Runs conatiner
- Manual restart
- Manual scaling
- Single host focus
- Manual networking

# Kubernetes
- Manages conatiner
- Self healing
- Automatic scaling
- Multi host focus
- Built-in service networking

# Without kubernetes
- Node service crashed
- app crahsed
- operational teams waked-up
- try to fix the problem manually
- restart the conatiners

# With Kubernetes
- Kubernetes detects the crashed
- Self healing
- Maintained desired counts
- Routes traffic only to healthy pods
- Scales up and down based on load
- No human intervention needed

# Key problems solved by kubernetes
- self healing
- scaling
- service discovery and networking
- zero downtime deployment
- infrastructure abstraction

# What is Borg?
Borg is an internal container orchestration system developed by Google.

# What Borg does
- Deploy containers automatically
- Restart if crash (self-healing)
- Scale based on demand
- Distribute load
- Efficient resource usage

# Kubernetes born in 2014 
Kubernetes is inspired by Google's internal system called Borg, which was used to manage containers at massive scale.

# What does K8s means?
Kubernetes is long to say , So engineers shorten it to : K+8+s

* Kubernetes started at Google to solve large scale conatiner management problems and become the global standard for running applications reliably in production.


# Kubernetes Architecture 
Kubernetes Cluster = Control Plane + Worker Nodes 

* Control Plane (Master Node) : 
- It is the brain of the Kubernetes cluster
- It makes decisions (scheduling, scaling, healing, etc.)
- It does NOT run containers, it only manages them

* Components of Control Plane :-
* 1. API Server : 
- It is the entry point of Kubernetes
- All requests (kubectl, UI, CI/CD tools) go through this

* 2. Scheduler : 
Decides which Node (worker machine) will run a Pod

* 3. Controller Manager :-
Controller Manager ensures system is always in desired state.”

* 4. etcd :- Databases of kubernetes, Stores all cluster data


* Worker nodes : 
Worker nodes are responsible for running applications in Kubernetes. They contain components like Kubelet, which ensures pods are running, Kube-proxy, which manages networking, and a container runtime like containerd to run containers.

⚙️ Components of Worker Node
1. Kubelet
- It is an agent running on every worker node
- Communicates with API Server

👉 Responsibilities:

- Makes sure containers are running
- Pulls container images
- Reports node status

👉 Simple line:

“Kubelet ensures pods are running correctly on the node.”

2. Kube-Proxy
- Handles networking inside the cluster

👉 Responsibilities:

- Maintains network rules
- Enables communication between pods
- Supports Services (ClusterIP, NodePort)

👉 Simple line:

“Kube-proxy manages networking between pods and services.”

3. Container Runtime
Software that actually runs containers

What is Replicas in Kubernetes?
👉 Replicas = Number of copies of a Pod running at the same time


# ⚡ What is kubectl?
👉 kubectl is the command-line tool (CLI) used to interact with a Kubernetes cluster.

# 🧠 What does kubectl do?
Using kubectl, you can:

- Create resources (Pods, Deployments, Services)
- View cluster information
- Update applications
- Debug issues
- Delete resources


# Commands :--

# kubectl version --client
This command is used to check the version of kubectl installed on your system (client only).

# kubectl get nodes 
This shows all nodes in your Kubernetes cluster

# kubectl config get-contexts
This shows all Kubernetes contexts configured on your system

# Pod 
- The actual running app(container wrapped in kubernetes layer).
- Pod is where your app lives and runs.
- It is the smallest deployable in kubernetes

# Deployment 
- It runs your app continuously.
- If the pod crashes , kubernetes restarts it automatically.
- If you want more copies(scaling), DEployment handles it.
- If you want zero downtime updates, Deployment does rolling updates.


# Deployments vs Controller Manager 
- Deployment is your instructions / descired state
- Controller manager is the worker that makes it happen
- You create deployment YAML -----> API server stores it -----> Controller Manager sees it -----> Controller Manager manages it 


# Services in k8s
* Without a service :--
- Your pod is not accessible
- Your app is invisible outside the cluster 
- Every time pod restarts , new IP address is assigned and old connection breaks.

* With services:-
- Gives your app a permanent IP.
- Lets other apps inside the cluster talk to it.
- Lets you expose it to the browser(NodePort) 

* Service -> Give my app a stable address so browser and other apps can reach it.

# Service Types :-
- Cluster IP 
- Node Port
- Load Balancer
- External Name 

* Cluster IP :- Exposes app inside the cluster only , won't accessible from browser . Useful when - backend talking to backend and Microservices communication .

* Node Port :- Exposes app on a node's IP + port. Makes app accessible from browser. Port range is of 30000-32767. It is generally used for local testing , demos and learning kubernetes.

* Load Balancer :-- Creates a cloud load balancer and gives public IP/DNS. It is mainly used to expose production applications on cloud platforms like Amazon Web Services, Microsoft Azure, and Google Cloud Platform.

* External Name : Maps Service to external DNS . Example : db.example.com
Used for external db or third party API.


