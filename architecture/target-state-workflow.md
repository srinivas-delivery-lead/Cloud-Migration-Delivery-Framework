# Target-State Cloud Workflow

```mermaid
flowchart LR
    U[Users / Channels] --> G[API Gateway]
    G --> S1[Service A]
    G --> S2[Service B]
    S1 --> DB1[(Managed Database)]
    S2 --> Q[Event / Message Layer]
    Q --> S3[Async Service]
    S3 --> DB2[(Data Store)]
    S1 --> O[Observability]
    S2 --> O
    S3 --> O
    CI[CI/CD Pipeline] --> S1
    CI --> S2
    CI --> S3
    IAM[Identity & Access] --> G
    IAM --> S1
    IAM --> S2
```

## Design checkpoints

- Loose coupling between services
- Stable API contracts
- Centralized identity and authorization
- Automated deployment and rollback
- Observable service health
- Resilience for downstream failures
- Managed secrets and configuration
- Defined RTO/RPO where required
