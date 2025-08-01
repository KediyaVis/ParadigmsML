# Module 3.1: Federated Learning – Strategy, Applications, and Constraints

## Overview

**Federated Learning (FL)** enables model training across multiple decentralized devices or data silos without transferring raw data. Instead, models are trained locally and only model updates (gradients) are shared and aggregated centrally.

This paradigm addresses:
- **Privacy concerns** in sensitive domains
- **Data ownership limitations**
- **Edge compute opportunities**

---

## How Federated Learning Works

### Step-by-step:
1. Central server initializes a global model
2. Local devices (clients) download the model
3. Each client trains locally using private data
4. Clients send encrypted updates to central server
5. Server aggregates updates to improve global model

Diagram:

```mermaid
sequenceDiagram
    participant Server
    participant Client1
    participant Client2
    participant Client3

    Server->>Client1: Send initial model
    Server->>Client2: Send initial model
    Server->>Client3: Send initial model

    Client1-->>Server: Send model update (gradient)
    Client2-->>Server: Send model update (gradient)
    Client3-->>Server: Send model update (gradient)

    Server->>Client1: Send updated global model
    Server->>Client2: Send updated global model
    Server->>Client3: Send updated global model
