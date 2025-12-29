# Kubernetes Notes

## Core Concepts
- Kubernetes orchestrates **containers** across multiple nodes
- Helps maintain **availability** and **load sharing**

---

## Nodes
- A **node** is a physical or virtual machine with Kubernetes installed
- Also called **worker node** or **minion**
- **Runs containers** deployed by Kubernetes
- If a node fails, applications on it go down → need **multiple nodes**

---

## Cluster
- A **cluster** is a group of nodes
- Benefits:
  - High availability
  - Load sharing
  - Fault tolerance

---

## Master / Control Plane
- Another node configured as **master**
- Responsibilities:
  - Watches over worker nodes
  - Orchestrates container workloads
  - Stores cluster information
  - Schedules and manages containers when nodes fail

---

## Kubernetes Components

### **API Server**
- Front-end of Kubernetes
- All tools (CLI, UI) communicate with it

### **etcd**
- Distributed, reliable **key-value store**
- Stores all cluster data
- Implements locks to avoid conflicts in multi-master setups

### **Scheduler**
- Assigns newly created containers/pods to nodes
- Distributes workload across nodes

### **Controllers**
- Orchestration “brain”
- Detect failures of nodes, containers, or endpoints
- Brings up new containers when needed

### **Container Runtime**
- Software to **run containers**
- Examples:
  - Docker (used in this course)
  - Alternatives: Rocket, CRI-O
- Runs containers on worker nodes

### **kubelet**
- Agent running on each **worker node**
- Ensures containers are running as expected
- Reports health information to master

---

## Master vs Worker Nodes
- **Master node**:
  - Runs **API Server**, **etcd**, **Scheduler**, **Controller Manager**
  - Orchestrates cluster and stores state
- **Worker node**:
  - Runs **kubelet** and **container runtime**
  - Hosts containers/pods
  - Communicates with master for health and instructions

---

## kubectl (Kubernetes CLI)
- Used to **deploy and manage applications**
- Used to **get cluster and node information**
- Common commands:
  - `kubectl run <app>` → deploy an application
  - `kubectl cluster-info` → view cluster information
  - `kubectl get nodes` → list all nodes

---

## Key Takeaways
- Node = machine running containers  
- Cluster = group of nodes  
- Master = manages cluster, orchestrates workloads  
- etcd = stores cluster state  
- Scheduler = assigns containers to nodes  
- Controllers = maintain desired state  
- Container runtime = runs containers  
- kubelet = node agent on workers  
- kubectl = CLI tool to interact with cluster

