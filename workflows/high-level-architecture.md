# High-Level Architecture Diagram Workflow

Create professional system architecture diagrams with **technology-specific icons**, **cloud infrastructure components**, and **mandatory documentation**.

---

## Mandatory Deliverables

**You MUST generate TWO files:**

1. **`[system-name]-architecture.drawio`** - The diagram with proper icons
2. **`[system-name]-architecture-docs.md`** - Architecture documentation

**DO NOT generate just one file. Both are required.**

---

## When to Use

- System design documentation
- Cloud infrastructure architecture
- Microservices topology
- Stakeholder presentations
- Technical reviews
- Architecture Decision Records (ADRs)

---

## Architecture Types

### 1. Cloud-Native / Microservices Architecture

**Components to show:**

- API Gateway (Kong, AWS API Gateway)
- Microservices (with technology stack)
- Databases (PostgreSQL, MongoDB, etc.)
- Message Queues (Kafka, RabbitMQ, SQS)
- Caching (Redis, ElastiCache)
- Cloud Services (AWS, Azure, GCP icons)

### 2. Three-Tier Architecture

**Components to show:**

- Presentation Layer (Web, Mobile)
- Application Layer (API, Business Logic)
- Data Layer (Database, Cache)

### 3. Event-Driven Architecture

**Components to show:**

- Event Producers
- Event Bus/Message Broker
- Event Consumers
- Event Store

---

## Process

### Step 1: Gather Requirements

Ask for:

- What is the system purpose?
- What are the main components?
- What technologies are used?
- What cloud provider (if any)?
- What are the key integrations?

### Step 2: Identify Components

**Map each component to an icon:**

| Component Type | Icon Style |
|---------------|-----------|
| Frontend (React, Vue) | Blue rounded rectangle with tech name |
| Mobile App | Phone shape |
| API Gateway | Purple hexagon or rectangle |
| Microservice | Green rounded rectangle with service name |
| Database | Cylinder with tech name |
| Cache | Red rounded rectangle (Redis) |
| Message Queue | Dark rectangle (Kafka) or orange (RabbitMQ) |
| Cloud Service | Use AWS/Azure/GCP specific icons |
| Load Balancer | Hexagon or AWS ELB icon |
| CDN | CloudFront icon or cloud shape |
| External Service | Yellow cloud |

### Step 3: Generate BOTH Outputs

**Output 1: Diagram (`[name]-architecture.drawio`)**
**Output 2: Documentation (`[name]-architecture-docs.md`)**

---

## Layout Rules

### Canvas Setup

- Width: **1600-2000px**
- Height: **1000-1400px**
- Grid: **10px**

### Layout Pattern (Left to Right)

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                   │
│  👤 Users     🌐 Frontend    ⚡ API Gateway    📦 Services        │
│                                                                   │
│  [Clients]  → [Web/Mobile] → [Gateway]     → [Microservices]    │
│                                            ↓                      │
│                                   [Databases] [Cache] [Queue]     │
│                                                                   │
│                          [External Services / Cloud]              │
│                                                                   │
└─────────────────────────────────────────────────────────────────┘
```

### Spacing

| Element | Spacing |
|---------|---------|
| Horizontal between layers | **180-220px** |
| Vertical between components | **100-150px** |
| Group padding | **40-60px** |

---

## Complete Diagram Example

Here is a complete XML structure for a microservices architecture:

```xml
<mxfile host="app.diagrams.net" modified="2024-01-01T00:00:00.000Z" agent="Claude" version="22.0.0">
  <diagram name="Architecture" id="architecture-diagram">
    <mxGraphModel dx="1422" dy="794" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1600" pageHeight="1200">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        
        <!-- ============ CLIENTS ============ -->
        
        <!-- User Actor -->
        <mxCell id="user" value="Users" style="shape=umlActor;verticalLabelPosition=bottom;verticalAlign=top;html=1;outlineConnect=0;fillColor=#f8cecc;strokeColor=#b85450;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="80" y="300" width="40" height="80" as="geometry"/>
        </mxCell>
        
        <!-- ============ FRONTEND LAYER ============ -->
        
        <!-- Frontend Container -->
        <mxCell id="frontend-layer" value="&lt;b&gt;Frontend Layer&lt;/b&gt;" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#e8f4fc;strokeColor=#6c8ebf;strokeWidth=2;verticalAlign=top;align=left;spacingLeft=10;fontSize=12;fontColor=#2d5f8a;fontStyle=1;" vertex="1" parent="1">
          <mxGeometry x="180" y="200" width="180" height="280" as="geometry"/>
        </mxCell>
        
        <!-- React Web App -->
        <mxCell id="web-app" value="&lt;b&gt;Web App&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;React + TypeScript&lt;/font&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#61DAFB;strokeColor=#21A1C4;fontColor=#1a1a1a;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="200" y="250" width="140" height="70" as="geometry"/>
        </mxCell>
        
        <!-- Mobile App -->
        <mxCell id="mobile-app" value="&lt;b&gt;Mobile App&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;React Native&lt;/font&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#61DAFB;strokeColor=#21A1C4;fontColor=#1a1a1a;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="200" y="350" width="140" height="70" as="geometry"/>
        </mxCell>
        
        <!-- ============ API GATEWAY ============ -->
        
        <!-- API Gateway -->
        <mxCell id="api-gateway" value="&lt;b&gt;API Gateway&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;Kong&lt;/font&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#5C4D7D;strokeColor=#4a3d68;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="440" y="305" width="140" height="70" as="geometry"/>
        </mxCell>
        
        <!-- ============ MICROSERVICES LAYER ============ -->
        
        <!-- Services Container -->
        <mxCell id="services-layer" value="&lt;b&gt;Microservices&lt;/b&gt;" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#e8f4ea;strokeColor=#82b366;strokeWidth=2;verticalAlign=top;align=left;spacingLeft=10;fontSize=12;fontColor=#2d5016;fontStyle=1;" vertex="1" parent="1">
          <mxGeometry x="660" y="150" width="400" height="380" as="geometry"/>
        </mxCell>
        
        <!-- Auth Service -->
        <mxCell id="auth-service" value="&lt;b&gt;Auth Service&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;Node.js + JWT&lt;/font&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#339933;strokeColor=#2d862d;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="690" y="200" width="140" height="60" as="geometry"/>
        </mxCell>
        
        <!-- User Service -->
        <mxCell id="user-service" value="&lt;b&gt;User Service&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;Node.js&lt;/font&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#339933;strokeColor=#2d862d;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="690" y="290" width="140" height="60" as="geometry"/>
        </mxCell>
        
        <!-- Order Service -->
        <mxCell id="order-service" value="&lt;b&gt;Order Service&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;Node.js&lt;/font&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#339933;strokeColor=#2d862d;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="690" y="380" width="140" height="60" as="geometry"/>
        </mxCell>
        
        <!-- Payment Service -->
        <mxCell id="payment-service" value="&lt;b&gt;Payment Service&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;Node.js&lt;/font&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#339933;strokeColor=#2d862d;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="890" y="200" width="140" height="60" as="geometry"/>
        </mxCell>
        
        <!-- Notification Service -->
        <mxCell id="notification-service" value="&lt;b&gt;Notification&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;Node.js&lt;/font&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#339933;strokeColor=#2d862d;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="890" y="290" width="140" height="60" as="geometry"/>
        </mxCell>
        
        <!-- ============ DATA LAYER ============ -->
        
        <!-- Data Container -->
        <mxCell id="data-layer" value="&lt;b&gt;Data Layer&lt;/b&gt;" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#f3e8f4;strokeColor=#9673a6;strokeWidth=2;verticalAlign=top;align=left;spacingLeft=10;fontSize=12;fontColor=#5c3d6e;fontStyle=1;" vertex="1" parent="1">
          <mxGeometry x="660" y="580" width="400" height="150" as="geometry"/>
        </mxCell>
        
        <!-- PostgreSQL -->
        <mxCell id="postgres-db" value="&lt;b&gt;PostgreSQL&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;Primary DB&lt;/font&gt;" style="shape=cylinder3;whiteSpace=wrap;html=1;boundedLbl=1;backgroundOutline=1;size=15;fillColor=#336791;strokeColor=#2d5a7d;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="690" y="620" width="100" height="80" as="geometry"/>
        </mxCell>
        
        <!-- MongoDB -->
        <mxCell id="mongo-db" value="&lt;b&gt;MongoDB&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;Documents&lt;/font&gt;" style="shape=cylinder3;whiteSpace=wrap;html=1;boundedLbl=1;backgroundOutline=1;size=15;fillColor=#47A248;strokeColor=#3d8a3d;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="810" y="620" width="100" height="80" as="geometry"/>
        </mxCell>
        
        <!-- Redis -->
        <mxCell id="redis-cache" value="&lt;b&gt;Redis&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;Cache&lt;/font&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#DC382D;strokeColor=#b52e25;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="930" y="630" width="100" height="60" as="geometry"/>
        </mxCell>
        
        <!-- ============ MESSAGE QUEUE ============ -->
        
        <!-- Kafka -->
        <mxCell id="kafka" value="&lt;b&gt;Apache Kafka&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;Event Streaming&lt;/font&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#231F20;strokeColor=#000000;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="890" y="380" width="140" height="60" as="geometry"/>
        </mxCell>
        
        <!-- ============ EXTERNAL SERVICES ============ -->
        
        <!-- Stripe -->
        <mxCell id="stripe" value="&lt;b&gt;Stripe API&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;Payments&lt;/font&gt;" style="ellipse;shape=cloud;whiteSpace=wrap;html=1;fillColor=#fff2cc;strokeColor=#d6b656;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="1140" y="190" width="140" height="80" as="geometry"/>
        </mxCell>
        
        <!-- SendGrid -->
        <mxCell id="sendgrid" value="&lt;b&gt;SendGrid&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;Email&lt;/font&gt;" style="ellipse;shape=cloud;whiteSpace=wrap;html=1;fillColor=#fff2cc;strokeColor=#d6b656;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="1140" y="290" width="140" height="80" as="geometry"/>
        </mxCell>
        
        <!-- ============ CONNECTIONS ============ -->
        
        <!-- User to Web -->
        <mxCell id="conn-user-web" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#333333;" edge="1" parent="1" source="user" target="web-app">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
        <!-- User to Mobile -->
        <mxCell id="conn-user-mobile" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#333333;" edge="1" parent="1" source="user" target="mobile-app">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
        <!-- Web to Gateway -->
        <mxCell id="conn-web-gateway" value="HTTPS" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#333333;labelBackgroundColor=#ffffff;fontSize=11;" edge="1" parent="1" source="web-app" target="api-gateway">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
        <!-- Mobile to Gateway -->
        <mxCell id="conn-mobile-gateway" value="HTTPS" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#333333;labelBackgroundColor=#ffffff;fontSize=11;" edge="1" parent="1" source="mobile-app" target="api-gateway">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
        <!-- Gateway to Services -->
        <mxCell id="conn-gateway-auth" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#333333;" edge="1" parent="1" source="api-gateway" target="auth-service">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
        <mxCell id="conn-gateway-user" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#333333;" edge="1" parent="1" source="api-gateway" target="user-service">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
        <mxCell id="conn-gateway-order" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#333333;" edge="1" parent="1" source="api-gateway" target="order-service">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
        <!-- Services to Databases -->
        <mxCell id="conn-user-postgres" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#336791;" edge="1" parent="1" source="user-service" target="postgres-db">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
        <mxCell id="conn-order-mongo" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#47A248;" edge="1" parent="1" source="order-service" target="mongo-db">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
        <!-- Services to Kafka (async) -->
        <mxCell id="conn-order-kafka" value="Events" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#d97706;dashed=1;dashPattern=8 8;labelBackgroundColor=#ffffff;fontSize=11;" edge="1" parent="1" source="order-service" target="kafka">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
        <mxCell id="conn-kafka-notification" value="Events" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#d97706;dashed=1;dashPattern=8 8;labelBackgroundColor=#ffffff;fontSize=11;" edge="1" parent="1" source="kafka" target="notification-service">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
        <!-- External connections -->
        <mxCell id="conn-payment-stripe" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#d6b656;" edge="1" parent="1" source="payment-service" target="stripe">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
        <mxCell id="conn-notification-sendgrid" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#d6b656;" edge="1" parent="1" source="notification-service" target="sendgrid">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
        <!-- Cache connections -->
        <mxCell id="conn-auth-redis" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#DC382D;" edge="1" parent="1" source="auth-service" target="redis-cache">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

---

## Documentation Template

**Save as: `[system-name]-architecture-docs.md`**

```markdown
# [System Name] Architecture Documentation

**Version:** 1.0  
**Date:** [Date]  
**Author:** [Author]

---

## 1. Overview

### 1.1 Purpose
[Brief description of what the system does]

### 1.2 Scope
[What is included in this architecture]

### 1.3 Architecture Style
[Microservices / Monolithic / Serverless / Event-Driven]

---

## 2. Architecture Diagram

See: `[system-name]-architecture.drawio`

**To view:**
1. Open [app.diagrams.net](https://app.diagrams.net)
2. File → Open → Select the `.drawio` file

---

## 3. Components

### 3.1 Frontend Layer

#### Web Application
- **Technology:** React 18 + TypeScript
- **Purpose:** Browser-based user interface
- **Deployment:** CloudFront + S3 (static hosting)
- **Key Features:**
  - Server-side rendering (Next.js)
  - State management (Redux Toolkit)
  - API calls via Axios

#### Mobile Application
- **Technology:** React Native
- **Purpose:** iOS and Android native apps
- **Deployment:** App Store / Play Store

### 3.2 API Gateway

#### Kong Gateway
- **Technology:** Kong 3.x
- **Purpose:** Central entry point for all API requests
- **Responsibilities:**
  - Request routing
  - Rate limiting
  - Authentication (JWT validation)
  - API versioning
  - Request/response transformation

### 3.3 Microservices

#### Auth Service
- **Technology:** Node.js 20 + Express
- **Purpose:** Authentication and authorization
- **Endpoints:**
  - `POST /auth/login`
  - `POST /auth/register`
  - `POST /auth/refresh`
  - `POST /auth/logout`
- **Dependencies:** Redis (session cache), PostgreSQL (user data)

#### User Service
- **Technology:** Node.js 20 + Express
- **Purpose:** User profile management
- **Endpoints:**
  - `GET /users/:id`
  - `PUT /users/:id`
  - `DELETE /users/:id`
- **Dependencies:** PostgreSQL

#### Order Service
- **Technology:** Node.js 20 + Express
- **Purpose:** Order management
- **Endpoints:**
  - `POST /orders`
  - `GET /orders/:id`
  - `PUT /orders/:id/status`
- **Dependencies:** MongoDB, Kafka (event publishing)

#### Payment Service
- **Technology:** Node.js 20 + Express
- **Purpose:** Payment processing
- **External Integration:** Stripe API
- **Endpoints:**
  - `POST /payments`
  - `GET /payments/:id`
  - `POST /payments/:id/refund`

#### Notification Service
- **Technology:** Node.js 20 + Express
- **Purpose:** Email and push notifications
- **External Integration:** SendGrid, Firebase Cloud Messaging
- **Event Consumer:** Listens to Kafka topics

### 3.4 Data Layer

#### PostgreSQL
- **Version:** 15
- **Purpose:** Relational data (users, auth, transactions)
- **Tables:** users, roles, permissions, audit_logs
- **HA:** Primary-replica setup with automatic failover

#### MongoDB
- **Version:** 6.0
- **Purpose:** Document storage (orders, products, inventory)
- **Collections:** orders, products, categories, inventory
- **Sharding:** Enabled for orders collection

#### Redis
- **Version:** 7.0
- **Purpose:** Caching and session storage
- **Use Cases:**
  - JWT session cache
  - API response cache
  - Rate limiting counters

### 3.5 Message Queue

#### Apache Kafka
- **Version:** 3.5
- **Purpose:** Event streaming and async communication
- **Topics:**
  - `order.created`
  - `order.updated`
  - `payment.completed`
  - `user.registered`

---

## 4. Data Flow

### 4.1 User Login Flow
1. User enters credentials in Web/Mobile app
2. Frontend sends POST /auth/login to API Gateway
3. API Gateway routes to Auth Service
4. Auth Service validates credentials against PostgreSQL
5. Auth Service creates JWT and stores session in Redis
6. JWT returned to client

### 4.2 Order Creation Flow
1. User submits order in frontend
2. API Gateway routes to Order Service
3. Order Service validates and saves to MongoDB
4. Order Service publishes `order.created` event to Kafka
5. Payment Service consumes event and initiates payment
6. Notification Service consumes event and sends confirmation email

---

## 5. Technology Stack

| Layer | Technology | Version | Justification |
|-------|-----------|---------|---------------|
| Frontend | React | 18.x | Component-based, large ecosystem |
| Mobile | React Native | 0.72 | Code sharing with web |
| API Gateway | Kong | 3.x | Plugin ecosystem, Kubernetes native |
| Backend | Node.js | 20 LTS | JavaScript fullstack, async I/O |
| Primary DB | PostgreSQL | 15 | ACID compliance, JSON support |
| Document DB | MongoDB | 6.0 | Flexible schema for orders |
| Cache | Redis | 7.0 | Sub-millisecond latency |
| Queue | Kafka | 3.5 | High throughput, durability |
| Container | Docker | 24.x | Containerization standard |
| Orchestration | Kubernetes | 1.28 | Cloud-native orchestration |

---

## 6. Security Considerations

### 6.1 Authentication
- JWT-based authentication with short-lived access tokens (15min)
- Refresh tokens stored in Redis with 7-day TTL
- Password hashing with bcrypt (cost factor 12)

### 6.2 Authorization
- Role-based access control (RBAC)
- Resource-level permissions
- API Gateway validates JWT before routing

### 6.3 Data Protection
- TLS 1.3 for all communications
- Data at rest encryption (AES-256)
- PII data stored in PostgreSQL with column-level encryption

### 6.4 Network Security
- VPC with private subnets for services
- Security groups limiting inter-service communication
- WAF at API Gateway level

---

## 7. Scalability

### 7.1 Horizontal Scaling
- All microservices are stateless and can scale horizontally
- Kubernetes HPA configured for CPU/memory thresholds
- Load balanced via Kubernetes Services

### 7.2 Database Scaling
- PostgreSQL: Read replicas for query scaling
- MongoDB: Sharding enabled for orders collection
- Redis: Cluster mode for high availability

### 7.3 Queue Scaling
- Kafka: Partition-based scaling
- Consumer groups for parallel processing

---

## 8. Deployment

### 8.1 Environment
- **Development:** Docker Compose locally
- **Staging:** Kubernetes on AWS EKS
- **Production:** Kubernetes on AWS EKS (multi-AZ)

### 8.2 CI/CD Pipeline
- GitHub Actions for CI
- ArgoCD for GitOps-based deployments
- Helm charts for Kubernetes manifests

### 8.3 Infrastructure as Code
- Terraform for AWS infrastructure
- Helm for Kubernetes resources

---

## 9. Monitoring & Observability

### 9.1 Logging
- Structured JSON logs
- Centralized logging with ELK stack
- Log levels: DEBUG, INFO, WARN, ERROR

### 9.2 Metrics
- Prometheus for metrics collection
- Grafana dashboards for visualization
- Key metrics: latency, throughput, error rate

### 9.3 Tracing
- Distributed tracing with Jaeger
- OpenTelemetry instrumentation
- Trace ID propagation across services

### 9.4 Alerting
- PagerDuty for on-call alerting
- Slack integration for notifications
- Runbooks for common incidents

---

## 10. Future Considerations

- [ ] GraphQL API layer
- [ ] Service mesh (Istio)
- [ ] Multi-region deployment
- [ ] Real-time features (WebSocket)

---

*Document generated by Architecture Diagrams Skill*
```

---

## Icon Quick Reference

### By Technology

| Technology | Fill | Stroke | Style |
|-----------|------|--------|-------|
| React | `#61DAFB` | `#21A1C4` | Rounded rectangle |
| Node.js | `#339933` | `#2d862d` | Rounded rectangle |
| PostgreSQL | `#336791` | `#2d5a7d` | Cylinder |
| MongoDB | `#47A248` | `#3d8a3d` | Cylinder |
| Redis | `#DC382D` | `#b52e25` | Rounded rectangle |
| Kafka | `#231F20` | `#000000` | Rectangle |
| API Gateway | `#5C4D7D` | `#4a3d68` | Rounded rectangle |
| External | `#fff2cc` | `#d6b656` | Cloud shape |

### Connection Types

| Type | Color | Style |
|------|-------|-------|
| HTTP/REST | `#333333` | Solid |
| Async/Event | `#d97706` | Dashed |
| Database | Match DB color | Solid |
| External | `#d6b656` | Solid |

---

## Pre-Generation Checklist

**Diagram:**

- [ ] All components have technology labels
- [ ] Proper icons used (not just rectangles)
- [ ] Layers are grouped and labeled
- [ ] Connections show protocol/type
- [ ] Colors are consistent
- [ ] External services clearly marked

**Documentation:**

- [ ] All components described
- [ ] Technology stack listed
- [ ] Data flow explained
- [ ] Security addressed
- [ ] Scalability covered
- [ ] Deployment notes included

---

## Output Files

**For a request like "Create architecture for e-commerce system":**

1. ✅ `ecommerce-architecture.drawio`
2. ✅ `ecommerce-architecture-docs.md`

**BOTH files are mandatory.**

---

*High-Level Architecture Diagrams - Professional system design documentation*
