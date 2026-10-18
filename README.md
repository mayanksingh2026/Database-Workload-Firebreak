# Database-Workload-Firebreak:-
A middleware-based system for multi-Application database workload governance, performance improvement, and workload protection.

## Problem:-
In a shared database environment, one application can generate excessive or resource-intensive requests. This can consume a large number of available resources and negatively affect the performance of other applications.This project introduces a workload governance layer that manages requests before they reach the shared database.

## Objectives:-
->  Provide Work Isolation Between Applications.So that one application on being overloaded does not affect others negatively using      resource limits, admission control, and per-Appliaction queues.
->Ensure Fair Resource Sharing instead of allowing one workload to monopolize resources using Weighted Round Robin scheduling.
->Control and Manage Database Workloads before allowing them to access the database using Process/Thread Scheduling, queues.
->Provide a monitoring dashboard to track Applications workloads, request status, resource usage, queue activity, and system performance metrics in real time using process/thread scheduling, resource management and database monitoring.

## Proposed Architecture:-
```markdown
```mermaid
flowchart LR
    Client["Client Applications"] --> Firebreak    
    subgraph Firebreak["Database Workload Firebreak (Middleware Layer)"]
        direction TB
        A["1. Application Identification"] --> 
        B["2. Workload Classification"] --> 
        C["3. Policy Engine"] --> 
        D["4. Admission Controller"] --> 
        E["5. Per-Application Queues"] --> 
        F["6. Weighted Scheduler"] --> 
        G["7. Worker Pool & Connection Manager"]
    end
    
    Firebreak --> DB["Shared Database"]
