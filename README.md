# Day1 Readme.md

## 1. Why is Docker helpful for microservices?
Docker makes it easier to build and run parts of an app (like in banking or online shopping) by doing the following:
Works the same everywhere: No matter where you run it—on your laptop, a test server, or live production—it behaves the same.
Keeps things separate: Each part of your app (like user login, payments, or product listings) runs in its own space so they don’t interfere with each other.
Fast and efficient: Uses less memory and starts faster than traditional virtual machines.
Works well with automation: Easy to plug into tools that automatically test and deploy your app (CI/CD).
Easy to move around: You can run Docker apps on any system that supports Docker.
Example: In an online store, Docker lets the payment system, user account system, and product catalog all run independently, making it easier to develop and manage them.

## 2. What’s the difference between a Docker image and a container (especially when scaling)?
Docker Image: Think of this like a recipe. It contains everything needed to run a service—like code and tools.
Docker Container: This is the actual dish made from the recipe—a live, running version of the image.
When you want to handle more users (scaling), you use the same image to run more containers.
Example: To handle a big sale, you might run 5 copies of your website’s frontend. All 5 come from the same image.

## 3. How Kubernetes helps Docker at a large scale
When your app gets big, Kubernetes (K8s) helps manage all the Docker containers. Here’s how:
Orchestrates everything: Decides where and when to run your containers.
Handles traffic: Shares the user load across different containers.
Heals itself: If something crashes, it restarts it automatically.
Grows with demand: Adds more containers when needed, and reduces when not.
No-downtime updates: Let's you update your app without taking it offline.
Example: In a banking app, Kubernetes makes sure the login system and transaction services are always running, stay updated, and handle thousands of users smoothly.

## Screenshot or log of Docker image being pushed
![image](https://github.com/user-attachments/assets/c85038fa-85cc-42a0-97fe-ecaefcb482bb)

#  Day2 Readme.md

## Explanation in README.md about affinity rules applied

- The pod will only be scheduled on nodes labeled with disktype=ssd.
- This is a hard rule — if no matching node is found, the pod won’t be scheduled.
- Useful for workloads that need specific hardware like SSDs.
- This helps ensure better performance and resource alignment for the application.

## Why do we set requests and limits for CPU/memory in a production-grade product?

- Prevents one app from using all the resources and slowing others down.  
- Helps keep apps stable and avoid crashes.  
- Helps plan how many servers you need.  
- Controls cloud costs by avoiding unexpected resource spikes.

## When would a product team apply node affinity in Kubernetes?

- When your app needs to run on special machines (e.g., with GPUs or SSDs).  
- When your app must be in a certain location or data center zone.  
- When you want to improve app speed and meet compliance rules.  
- Node affinity tells Kubernetes where to put your app based on machine features.

##  Screenshot or logs showing the running pod and node placement
![image](https://github.com/user-attachments/assets/034bfadf-b42f-4566-b5b9-62b42149c996)



# Day3 Readme.md

## Screenshot of working endpoint via Ingress (use Minikube ingress if on local)

![image](https://github.com/user-attachments/assets/cdbbc3bf-d698-4a54-aeb9-b2b0e97b7be2)


## How would you expose an internal microservice (e.g., user-auth) differently than a public-facing frontend in a Kubernetes-based product?

In a Kubernetes-based product, internal microservices (e.g., user-auth) and public-facing frontends are exposed differently to maintain security, manage traffic efficiently, and simplify networking.
Internal Microservices (e.g., user-auth)
These services typically do not need to be accessed directly from outside the cluster. Instead, they are exposed only within the Kubernetes cluster or a private network. Common approaches include:
Using ClusterIP services (default), which are only accessible inside the cluster.
Accessing them through other microservices or APIs via service discovery or internal DNS.
Optionally using Network Policies to restrict which pods or namespaces can communicate with them.


## Why might a product use Ingress instead of directly exposing each microservice via LoadBalancer?


Using an Ingress to expose services instead of creating a LoadBalancer for each microservice is generally preferred because:
Cost Efficiency
Cloud providers charge for each LoadBalancer resource. Using one Ingress LoadBalancer to route traffic to many services reduces costs.
Centralized Traffic Management
Ingress controllers provide a single entry point for HTTP/HTTPS traffic. This simplifies configuration for SSL/TLS termination, URL path-based routing, and host-based routing.
Improved Security
TLS certificates and security policies can be centrally managed at the Ingress level rather than on every LoadBalancer service.
Simplified DNS and Networking
One external IP or hostname can be used for multiple services by routing traffic internally based on paths or hostnames.
Advanced Features
Ingress controllers often support rate limiting, authentication, retries, and can integrate with API gateways or service meshes for more advanced traffic control.




# Day4 Readme.md

Screenshot of Helm install and upgrade commands
![image](https://github.com/user-attachments/assets/f10df980-79b3-4723-a23a-0cdea3164fa5)





 
