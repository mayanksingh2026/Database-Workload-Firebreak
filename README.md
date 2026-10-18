# Database-Workload-Firebreak:-
A middleware-based system for multi-Application database workload governance, performance improvement, and workload protection.

## Problem:-
In a shared database environment, one application can generate excessive or resource-intensive requests. This can consume a large number of available resources and negatively affect the performance of other applications.This project introduces a workload governance layer that manages requests before they reach the shared database.

## Objectives:-
- **1.Work Isolation**  
  Isolate workloads between applications so that an overloaded application cannot negatively impact others. This is achieved through resource limits, admission control, and per-application queues.

- **2.Fair Resource Sharing**  
  Ensure fair distribution of database resources using Weighted Round Robin scheduling, preventing any single workload from monopolizing system resources.

- **3.Controlled Workload Management**  
  Manage and control database workloads before they reach the shared database using process/thread scheduling and queuing mechanisms.

- **4.Real-time Monitoring**  
  Provide a monitoring dashboard to track application workloads, request status, resource usage, queue activity, and overall system performance in real time.

## Proposed Architecture:-
```mermaid
flowchart TD
    Client["Client Applications"]
    
    subgraph Firebreak["Database Workload Firebreak<br/>(Middleware Layer)"]
        direction TB
        A["1. Application Identification"]
        B["2. Workload Classification"]
        C["3. Policy Engine"]
        D["4. Admission Controller"]
        E["5. Per-Application Queues"]
        F["6. Weighted Scheduler"]
        G["7. Worker Pool & Connection Manager"]
        
        A --> B --> C --> D --> E --> F --> G
    end
    
    DB["Shared Database"]
    
    Client --> Firebreak
    Firebreak --> DB
