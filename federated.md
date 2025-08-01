# Module 3.1: Federated Learning – Strategy, Applications, and Real-World Deployment

## Learning Objectives
- Understand the concept, workflow, and strategic role of Federated Learning (FL)
- Identify domains where FL addresses privacy, decentralization, and compute constraints
- Empower data scientists to evaluate FL as a deployment paradigm for sensitive data use cases

---

## What is Federated Learning?

Federated Learning is a decentralized machine learning approach that enables model training across multiple data sources without centralizing data. This is achieved by sending the model to each device or node, training locally, and aggregating learned updates.

### Key Principles
- **Privacy-first modeling:** Data never leaves its source
- **On-device intelligence:** Computation performed locally
- **Secure aggregation:** Model updates (not raw data) are sent to a central server

---

## Workflow Overview

```mermaid
sequenceDiagram
    participant CentralServer
    participant ClientA
    participant ClientB
    participant ClientC

    CentralServer->>ClientA: Distribute initial model
    CentralServer->>ClientB: Distribute initial model
    CentralServer->>ClientC: Distribute initial model

    ClientA-->>CentralServer: Send trained updates
    ClientB-->>CentralServer: Send trained updates
    ClientC-->>CentralServer: Send trained updates

    CentralServer->>All Clients: Broadcast updated global model
