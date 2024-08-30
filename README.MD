## Project Description: Priority-Based Process Scheduling for Distributed E-commerce Platforms

You are a software developer for a major e-commerce platform that processes millions of transactions per day. The platform operates on a distributed system with multiple servers, each running distinct services tailored to specific types of transactions. Your role involves designing a process scheduling algorithm optimized for efficiency and scalability.

### System Architecture

- **Multiple Servers**: Each server runs a service that handles a particular type of transaction, such as payment processing or order handling.
- **Worker Threads**: Each service is supported by a pool of worker threads. Each thread is assigned:
  - **Priority Level**: Dictates the scheduling order of threads for processing requests.
  - **Resources**: Determines how many requests a thread can concurrently manage.

### Request Handling

- **Request Queueing**: Incoming requests are first queued and then assigned to the appropriate service based on the transaction type.
- **Thread Assignment**: Within services, requests are queued further and assigned to worker threads based on priority levels.

### Algorithm Design Task

Your task is to develop a process scheduling algorithm that:
- **Efficient Resource Allocation**: Allocates resources to worker threads for processing incoming requests efficiently.
- **Priority Consideration**: Prioritizes higher-priority threads for resource allocation. If such threads are unavailable, the algorithm defaults to the next available thread with a lower priority.
- **Transaction Type Awareness**: Accounts for the resource demands varying by transaction type, as some transactions (like payment processing) may need more resources than others (like order processing).

### Input/Output Specifications

- **Input**:
  - The number of services (`n`) in the system.
  - The number of worker threads (`m`) for each service.
  - Priority level and resources for each worker thread in the format: `priority_level resources`.
  - Type of transaction and resources required for each request in the format: `transaction_type resources_required`.

- **Output**:
  - Order in which requests were processed.
  - Average waiting time for requests.
  - Average turnaround time for requests.
  - Number of requests rejected due to resource shortages.

### High Traffic Handling

During peak periods, the program should additionally output:
- Number of requests delayed due to resource shortages.
- Number of requests blocked due to all worker threads being occupied.
