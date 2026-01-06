---
name: architecture-diagrams
description: Create professional software architecture diagrams with proper icons, documentation, and deliverables. Generates Draw.io diagrams AND accompanying documentation. USE WHEN user asks for architecture, system design, ERD, sequence diagrams, or technical documentation.
---

# Software Architecture & Documentation Skill

Create production-ready architecture diagrams with **proper icons**, **technology-specific visuals**, and **comprehensive documentation** - ready for stakeholder presentations and technical reviews.

---

## What This Skill Delivers

This skill generates **TWO outputs** for every request:

### 1. Draw.io Diagram File (`.drawio`)

- Professional diagrams with **technology-specific icons**
- AWS, Azure, GCP, Kubernetes, Docker icons
- Framework icons (React, Node.js, Python, Java, etc.)
- Database icons (PostgreSQL, MongoDB, Redis, etc.)
- Proper UML notation where applicable

### 2. Documentation File (`.md`)

- Component descriptions
- Data flow explanations
- Technology decisions
- API contracts (where applicable)
- Deployment notes

---

## Diagram Types

| Diagram Type | Use For | Workflow |
|--------------|---------|----------|
| **High-Level Architecture** | System overview, cloud infrastructure, microservices topology | [workflows/high-level-architecture.md](workflows/high-level-architecture.md) |
| **Low-Level Architecture** | Class diagrams, module structure, design patterns | [workflows/low-level-architecture.md](workflows/low-level-architecture.md) |
| **Sequence Diagrams** | API flows, service interactions, message passing | [workflows/sequence-diagram.md](workflows/sequence-diagram.md) |
| **Entity Diagrams (ERD)** | Database schema, data models, relationships | [workflows/entity-diagram.md](workflows/entity-diagram.md) |
| **Deployment Diagrams** | Infrastructure, containers, CI/CD pipelines | [workflows/deployment-diagram.md](workflows/deployment-diagram.md) |
| **API Documentation** | REST/GraphQL endpoints, request/response schemas | [workflows/api-documentation.md](workflows/api-documentation.md) |

---

## Mandatory Deliverables

**For EVERY diagram request, Claude MUST generate:**

1. **Diagram file** (`[name].drawio`) with proper icons
2. **Documentation file** (`[name]-docs.md`) with:
   - Overview/Purpose
   - Component descriptions
   - Data flow explanation
   - Technology stack
   - Key decisions/rationale

---

## Workflow Routing

**Step 1: Identify diagram type from user request**

| User Says | Diagram Type | LOAD THIS WORKFLOW |
|-----------|--------------|---------------------|
| "architecture", "system design", "high level", "microservices", "cloud" | High-Level Architecture | **READ: [workflows/high-level-architecture.md](workflows/high-level-architecture.md)** |
| "class diagram", "low level", "detailed design", "module", "components" | Low-Level Architecture | **READ: [workflows/low-level-architecture.md](workflows/low-level-architecture.md)** |
| "sequence", "API flow", "interaction", "message flow", "request/response" | Sequence Diagram | **READ: [workflows/sequence-diagram.md](workflows/sequence-diagram.md)** |
| "ERD", "database", "schema", "data model", "tables", "entities" | Entity Diagram | **READ: [workflows/entity-diagram.md](workflows/entity-diagram.md)** |
| "deployment", "infrastructure", "CI/CD", "containers", "kubernetes" | Deployment Diagram | **READ: [workflows/deployment-diagram.md](workflows/deployment-diagram.md)** |
| "API docs", "endpoints", "REST", "GraphQL", "swagger" | API Documentation | **READ: [workflows/api-documentation.md](workflows/api-documentation.md)** |

**Step 2: Load core references (ALWAYS)**

Before generating ANY diagram, also READ these files:

1. **[references/drawio-format.md](references/drawio-format.md)** - XML structure and shape definitions
2. **[references/icon-library.md](references/icon-library.md)** - Technology icons and shapes
3. **[references/colors.md](references/colors.md)** - Color palettes

**Step 3: Generate BOTH outputs**

1. Generate the `.drawio` file with proper icons
2. Generate the `-docs.md` file with documentation

---

## Icon Library

### Cloud Providers

- **AWS:** EC2, S3, Lambda, RDS, ECS, EKS, API Gateway, CloudFront, SQS, SNS
- **Azure:** App Service, Azure Functions, Cosmos DB, AKS, API Management
- **GCP:** Compute Engine, Cloud Run, Cloud Functions, Firestore, GKE

### Technologies

- **Frontend:** React, Vue, Angular, Next.js, iOS, Android
- **Backend:** Node.js, Python, Java, Go, .NET, Spring Boot
- **Databases:** PostgreSQL, MySQL, MongoDB, Redis, Elasticsearch, Cassandra
- **Messaging:** Kafka, RabbitMQ, SQS, Pub/Sub
- **Containers:** Docker, Kubernetes, Helm

### Infrastructure

- **Load Balancers:** nginx, HAProxy, AWS ALB, Cloudflare
- **API Gateways:** Kong, AWS API Gateway, Apigee
- **Monitoring:** Prometheus, Grafana, DataDog, New Relic

---

## Example Requests

### High-Level Architecture

```
"Create a high-level architecture diagram for a video streaming platform using:
- React frontend
- Node.js microservices
- PostgreSQL and Redis
- AWS (S3, CloudFront, ECS)
- Kafka for event streaming

Include proper AWS icons and generate documentation."
```

### Low-Level Architecture

```
"Create a class diagram for an order processing service showing:
- OrderController, OrderService, OrderRepository
- Interfaces and implementations
- Repository pattern with dependency injection
- Include TypeScript/Node.js patterns

Generate documentation explaining the design."
```

### Sequence Diagram

```
"Create a sequence diagram for OAuth 2.0 authentication flow:
- User, React Frontend, API Gateway, Auth Service, User Database
- Show token generation and validation
- Include error handling for invalid credentials

Generate API documentation for the endpoints involved."
```

### Deployment Diagram

```
"Create a Kubernetes deployment diagram for a microservices application:
- 3 services with their pods
- Ingress controller
- ConfigMaps and Secrets
- PostgreSQL StatefulSet
- Redis deployment

Include Kubernetes icons and generate deployment documentation."
```

---

## Output Structure

For a request like "Create architecture for e-commerce system":

### Files Generated

1. **`ecommerce-architecture.drawio`**
   - Diagram with AWS/technology icons
   - Proper layering and grouping
   - Clear data flow arrows

2. **`ecommerce-architecture-docs.md`**
   - System Overview
   - Component Descriptions
   - Data Flow
   - Technology Stack
   - Security Considerations
   - Scalability Notes

---

## Documentation Template

Every documentation file MUST include:

```markdown
# [System Name] Architecture Documentation

## 1. Overview
Brief description of the system and its purpose.

## 2. Architecture Diagram
Reference to the .drawio file with viewing instructions.

## 3. Components

### 3.1 [Component Name]
- **Purpose:** What it does
- **Technology:** Stack used
- **Responsibilities:** Key functions
- **Dependencies:** What it connects to

### 3.2 [Next Component]
...

## 4. Data Flow
Step-by-step explanation of how data moves through the system.

## 5. Technology Stack
| Layer | Technology | Justification |
|-------|-----------|---------------|
| Frontend | React | ... |
| Backend | Node.js | ... |
| Database | PostgreSQL | ... |

## 6. API Contracts (if applicable)
Key endpoints and their purposes.

## 7. Security Considerations
Authentication, authorization, encryption.

## 8. Scalability
How the system scales horizontally/vertically.

## 9. Deployment
Environment requirements and deployment process.
```

---

## Skill Structure

```
architecture-diagrams/
├── SKILL.md (this file)
├── workflows/
│   ├── high-level-architecture.md    ← System overview with icons
│   ├── low-level-architecture.md     ← Class/module diagrams
│   ├── sequence-diagram.md           ← Interaction flows
│   ├── entity-diagram.md             ← Database schemas
│   ├── deployment-diagram.md         ← Infrastructure/K8s
│   └── api-documentation.md          ← API specs
└── references/
    ├── drawio-format.md              ← XML structure
    ├── icon-library.md               ← Technology icons
    └── colors.md                     ← Color schemes
```

---

## Quality Checklist

Before delivering, verify:

**Diagram:**

- [ ] Uses proper technology icons (not just rectangles)
- [ ] Has clear component labels
- [ ] Shows data flow with arrows
- [ ] Uses consistent colors
- [ ] Groups related components
- [ ] Includes legend if needed

**Documentation:**

- [ ] Covers all components in diagram
- [ ] Explains data flow
- [ ] Lists technology stack
- [ ] Includes API details (if applicable)
- [ ] Has security considerations
- [ ] Provides deployment notes

---

## Tips for Best Results

1. **Specify technologies** - "React frontend, Node.js API" not just "frontend and backend"
2. **Mention cloud provider** - "Using AWS" or "Deploy on Kubernetes"
3. **List key components** - Give Claude the context upfront
4. **Request both outputs** - "Generate diagram AND documentation"
5. **Iterate** - "Add caching layer" or "Show more detail on the API service"

---

*Architecture Diagrams Skill - Professional deliverables for software engineering*
