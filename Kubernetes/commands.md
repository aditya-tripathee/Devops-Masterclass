# kubectl get pods
This commands show the pods 

# kubectl create deployment web --image=nginx
👉 This creates a Deployment named web using the nginx image

* Now going to expose my app nginx
# kubectl expose deployment web --type=NodePort --port=80


# kubectl get svc 
* It displays:
- Service Name
- Type (ClusterIP, NodePort, LoadBalancer)
- Cluster IP
- External IP (if available)
- Ports
- Age

# kubectl get svc web
kubectl get svc web is used to get details of a specific service named web.



# kubectl delete pod web-64c966cf88-r5vsr
Delete (remove) this specific pod named web-64c966cf88-r5vsr

# Interview Questions 
"If there is only one pod and we delete it, the behavior depends on how it was created. If it is a standalone pod, it will be deleted permanently. But if it is managed by a Deployment or ReplicaSet, Kubernetes will automatically recreate a new pod to maintain the desired state."

# 🧠 What is a ReplicaSet?
👉 ReplicaSet is a Kubernetes controller that ensures a fixed number of identical Pods are always running.

# kubectl get rs
It tells the kubernetes to show me all the ReplicaSets in the current namespace.

# kubectl describe rs web-64c966cf88
It tells Kubernetes to give me detailed information about the ReplicaSet named web-64c966cf88.

# Scaling pods
- 🚀 Scaling Pods in Kubernetes
- 
- 👉 Scaling = Increasing or decreasing the number of Pods running for your application.
- 
- 🧠 Why do we scale?
- Handle more traffic 📈
- Reduce load on each pod ⚖️
- Save resources when traffic is low 📉

# 🎤 Interview Style Answer
"Scaling in Kubernetes means increasing or decreasing the number of pod replicas. It is done using Deployments or ReplicaSets by updating the replicas field. Kubernetes then ensures the desired number of pods are running. Scaling can be manual or automatic using Horizontal Pod Autoscaler."

