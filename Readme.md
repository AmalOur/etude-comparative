# Eureka vs Consul - Comparative Study  

This project provides a comparative analysis of **Eureka** and **Consul** for service discovery in a microservices architecture. Each service's implementation—**Feign**, **RestTemplate**, and **WebClient**—is available in separate branches for clarity and ease of testing.  


---

## Table of Contents  
1. [Architecture](#architecture)  
2. [Branches](#branches)  
3. [Performance Analysis](#performance-analysis)  
4. [Getting Started](#getting-started)  
5. [Contributors](#contributors)  

---

## Architecture  


The application is designed with the following components:  
![image](https://github.com/user-attachments/assets/438b2c87-728e-4a99-a374-bf82850a4e5c)

- **Service Clients** (Feign, RestTemplate, and WebClient) for communication between services.  
- **Discovery Servers**:  
  - Eureka: A Netflix OSS-based solution.  
  - Consul: A HashiCorp-based solution.  
- **Supporting Tools**:  
  - Kubernetes for orchestration.  
  - Prometheus and Grafana for monitoring.  
  - Apache JMeter for load testing.  

---

## Branches  

Each branch contains the implementation for a specific service client:  
- **Feign**: Branch `feign`.  
- **RestTemplate**: Branch `rest-template`.  
- **WebClient**: Branch `webclient`.  

To switch to a specific branch:  
```bash  
git checkout <branch-name>  
```  

---

## Performance Analysis  

### Response Time and Throughput  

| **Service Client** | **Eureka (ms/req)** | **Consul (ms/req)** | **Eureka (req/s)** | **Consul (req/s)** |  
|---------------------|---------------------|---------------------|---------------------|---------------------|  
| **RestTemplate**   | 220                 | 240                 | 150                 | 130                 |  
| **Feign**          | 180                 | 190                 | 220                 | 200                 |  
| **WebClient**      | 150                 | 160                 | 260                 | 240                 |  

### Resource Consumption  

| **Service Client** | **CPU Usage (Eureka)** | **Memory Usage (Eureka)** | **CPU Usage (Consul)** | **Memory Usage (Consul)** |  
|---------------------|-----------------------|---------------------------|-----------------------|---------------------------|  
| **RestTemplate**   | 75%                   | 280 MB                    | 80%                   | 300 MB                    |  
| **Feign**          | 65%                   | 250 MB                    | 70%                   | 260 MB                    |  
| **WebClient**      | 60%                   | 220 MB                    | 65%                   | 230 MB                    |  

### Key Observations  
- **WebClient** consistently outperforms the other clients in terms of response time and throughput.  
- Resource consumption is slightly higher with Consul compared to Eureka.  

---

## Getting Started  

### Local Setup  
Clone the repository:  
```bash  
git clone https://github.com/AmalOur/etude-comparative-service.git  
cd etude-comparative-service  
```  

Start the services:  
```bash  
docker-compose up --build  
```  

Access the services  

---

## Contributors  

- **Amal Ourajim** (GitHub: [AmalOur](https://github.com/AmalOur))  
- **Mohamed Lachgar** (ResearchGate: [M. Lachgar](https://www.researchgate.net/profile/Mohamed-Lachgar))  

---

Feel free to contribute and share your feedback to enhance this project!
