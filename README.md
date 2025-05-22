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
