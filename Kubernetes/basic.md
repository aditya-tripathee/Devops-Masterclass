* Docker solved "it works on my machine" by packaging the dependencies and apps into containers.

# Orchestration 
It means automatcially managing many containers across machines - including running , scaling , networking and healing them.



# Why we need orchestration ?
* We need orchestration because managing a small number of containers (like 5–6) can be done manually, but in real-world applications we often have hundreds of containers. It becomes very difficult to monitor, restart, scale, and distribute traffic manually.

* Orchestration tools (like Kubernetes) automate this process by handling container deployment, scaling, load balancing, and self-healing, ensuring the system runs efficiently and reliably.


# Kubernetes
* A conatiner orchestration platform that manages conatiners for you at scale.
* It automates deployment, scaling , healing , networking and management of containerized applications.


# Docker 
* Runs conatiner
* Manual restart
* Manual scaling 
* Single host focus
* Manual networking


# Kubernetes
* Manages conatiner
* Self healing
* Automatic scaling 
* Multi host focus
* Built-in service networking


# Without kubernetes
* Node service crashed
* app crahsed
* operational teams waked-up 
* try to fix the problem manually
* restart the conatiners

# With Kubernetes
* Kubernetes detects the crashed
* Self healing 
* Maintained desired counts
* Routes traffic only to healthy pods
* Scales up and down based on load
* No human intervention needed


# Key problems solved by kubernetes
* self healing
* scaling 
* service discovery and networking
* zero downtime deployment
* infrastructure abstraction


