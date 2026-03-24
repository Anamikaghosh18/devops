# 🐳 Docker Network 

## Overview

Docker networking allows containers to communicate with each other, the host system, and external networks.

- Demo project: This project uses a **user-defined bridge network (`two-tier`)** to enable communication between:

* Flask Backend (Application Layer)
* MySQL Database (Data Layer)

🔗 GitHub Repository:

> [https://github.com/Anamikaghosh18/devops-two-tier-app](https://github.com/Anamikaghosh18/devops-two-tier-app)


## 🔹 Types of Docker Networks

### 1. Host Network

* Container shares the host’s network stack
* No isolation between container and host
* Faster performance (no NAT)

Use case:

* High-performance applications



### 2. Bridge Network (Default)

* Default network created by Docker
* Containers get private IPs
* Communication via IP address

Limitation:

* No automatic DNS (container name resolution not reliable)


### 3. User-Defined Bridge Network 

* Custom bridge network created by user
* Provides **automatic DNS resolution**
* Containers can communicate using **container names**

Use case:

* Multi-container apps (Flask ↔ MySQL)

### 4. None Network

* Completely isolates container
* No external or internal network access

Use case:

* Security testing


### 5. MACVLAN

* Assigns MAC address to container
* Appears as physical device on network

Use case:

* Legacy apps requiring direct network access


### 6. IPVLAN

* Similar to MACVLAN but more efficient
* Shares MAC address but different IPs

### 7. Overlay Network

* Used in Docker Swarm
* Connects containers across multiple hosts

Use case:

* Distributed systems


## Basic Commands

### List networks

```bash
docker network ls
```

### Create a network

```bash
docker network create --driver bridge two-tier
```

### Inspect a network

```bash
docker network inspect two-tier
```

### Remove a network

```bash
docker network rm two-tier
```


