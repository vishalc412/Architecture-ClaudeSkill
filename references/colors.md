# Enterprise Architecture Color Reference

Professional color palette for architecture diagrams, technical documentation, and stakeholder presentations.

---

## Core Design Principles

1. **Muted & Professional** - Avoid saturated, childish colors
2. **Consistent Semantics** - Color meaning should be universal across diagrams
3. **Accessibility First** - Minimum 4.5:1 contrast ratio for text
4. **Cloud-Native Alignment** - Respect official brand colors for cloud providers

---

## Primary Architecture Colors

Use these for core diagram components:

| Category | Background | Stroke | Text | Use For |
|----------|------------|--------|------|---------|
| Primary | `#E8F4FD` | `#1565C0` | `#0D47A1` | Core services, main flow |
| Secondary | `#F3E5F5` | `#7B1FA2` | `#4A148C` | Supporting services |
| Tertiary | `#E0F2F1` | `#00796B` | `#004D40` | Infrastructure components |
| Neutral | `#FAFAFA` | `#616161` | `#424242` | Generic containers, groups |
| Accent | `#FFF8E1` | `#F57C00` | `#E65100` | Highlights, key decisions |

---

## Cloud Provider Official Colors

### AWS (Amazon Web Services)

| Service Category | Background | Stroke/Icon | Use For |
|------------------|------------|-------------|---------|
| Compute | `#FFEBCC` | `#FF9900` | EC2, Lambda, ECS |
| Storage | `#E6F2E6` | `#3F8624` | S3, EBS, Glacier |
| Database | `#E6E6FF` | `#3B48CC` | RDS, DynamoDB, Aurora |
| Networking | `#F2E6FF` | `#8C4FFF` | VPC, Route53, CloudFront |
| Security | `#FFE6E6` | `#DD344C` | IAM, KMS, Secrets Manager |
| Analytics | `#E6F0FF` | `#4D72C3` | Redshift, Athena, Kinesis |

### Azure (Microsoft Azure)

| Service Category | Background | Stroke/Icon | Use For |
|------------------|------------|-------------|---------|
| Compute | `#E6F3FF` | `#0078D4` | VMs, App Service, Functions |
| Storage | `#E6F3FF` | `#0078D4` | Blob, Files, Queues |
| Database | `#E6F3FF` | `#0078D4` | SQL, Cosmos DB |
| Networking | `#E6F3FF` | `#0078D4` | VNet, Load Balancer |
| AI/ML | `#FFF0E6` | `#FF8C00` | Cognitive Services, ML |
| DevOps | `#E6F3FF` | `#0078D4` | Azure DevOps, Pipelines |

### GCP (Google Cloud Platform)

| Service Category | Background | Stroke/Icon | Use For |
|------------------|------------|-------------|---------|
| Compute | `#E8F0FE` | `#4285F4` | Compute Engine, Cloud Run |
| Storage | `#E8F0FE` | `#4285F4` | Cloud Storage, Filestore |
| Database | `#E8F0FE` | `#4285F4` | Cloud SQL, Spanner, BigQuery |
| Networking | `#E8F0FE` | `#4285F4` | VPC, Load Balancing, CDN |
| AI/ML | `#FCE8E6` | `#EA4335` | Vertex AI, AutoML |
| Data/Analytics | `#E6F4EA` | `#34A853` | Dataflow, Pub/Sub |

---

## Technology Stack Colors

### Frontend Technologies

| Technology | Background | Stroke | Use For |
|------------|------------|--------|---------|
| React | `#E3F2FD` | `#61DAFB` | React components, SPAs |
| Angular | `#FFEBEE` | `#DD0031` | Angular applications |
| Vue.js | `#E8F5E9` | `#42B883` | Vue.js components |
| Next.js | `#F5F5F5` | `#000000` | Next.js applications |

### Backend Technologies

| Technology | Background | Stroke | Use For |
|------------|------------|--------|---------|
| Node.js | `#E8F5E9` | `#339933` | Node.js services |
| Python | `#FFF8E1` | `#3776AB` | Python services, ML |
| Java/Spring | `#FFF3E0` | `#6DB33F` | Enterprise Java services |
| .NET | `#EDE7F6` | `#512BD4` | .NET applications |
| Go | `#E0F7FA` | `#00ADD8` | Go microservices |

### Infrastructure & DevOps

| Technology | Background | Stroke | Use For |
|------------|------------|--------|---------|
| Docker | `#E3F2FD` | `#2496ED` | Containers |
| Kubernetes | `#E8EAF6` | `#326CE5` | K8s clusters, pods |
| Terraform | `#EDE7F6` | `#7B42BC` | Infrastructure as Code |
| Jenkins | `#FFEBEE` | `#D33833` | CI/CD pipelines |
| GitHub Actions | `#F5F5F5` | `#2088FF` | Workflows |

### Databases

| Technology | Background | Stroke | Use For |
|------------|------------|--------|---------|
| PostgreSQL | `#E3F2FD` | `#336791` | PostgreSQL instances |
| MongoDB | `#E8F5E9` | `#47A248` | MongoDB clusters |
| Redis | `#FFEBEE` | `#DC382D` | Redis caches |
| Elasticsearch | `#FFF8E1` | `#FEC514` | Search/analytics |

### Messaging & Streaming

| Technology | Background | Stroke | Use For |
|------------|------------|--------|---------|
| Kafka | `#F5F5F5` | `#231F20` | Event streaming |
| RabbitMQ | `#FFF3E0` | `#FF6600` | Message queues |
| Redis Pub/Sub | `#FFEBEE` | `#DC382D` | Real-time messaging |

---

## Swimlane & Layer Colors

For architectural layers and swimlanes:

| Layer | Header Background | Header Text | Lane Background |
|-------|-------------------|-------------|-----------------|
| Presentation | `#1565C0` | `#FFFFFF` | `#E3F2FD` |
| Application | `#2E7D32` | `#FFFFFF` | `#E8F5E9` |
| Business Logic | `#7B1FA2` | `#FFFFFF` | `#F3E5F5` |
| Data Access | `#E65100` | `#FFFFFF` | `#FFF3E0` |
| Infrastructure | `#455A64` | `#FFFFFF` | `#ECEFF1` |
| External Systems | `#5D4037` | `#FFFFFF` | `#EFEBE9` |

---

## Status & State Indicators

| Status | Background | Stroke | Icon Color | Use For |
|--------|------------|--------|------------|---------|
| Active/Running | `#E8F5E9` | `#2E7D32` | `#1B5E20` | Healthy services |
| Pending/In Progress | `#FFF8E1` | `#F9A825` | `#F57F17` | Deploying, processing |
| Warning | `#FFF3E0` | `#EF6C00` | `#E65100` | Performance issues |
| Error/Critical | `#FFEBEE` | `#C62828` | `#B71C1C` | Failures, outages |
| Inactive/Stopped | `#ECEFF1` | `#607D8B` | `#455A64` | Disabled services |
| Deprecated | `#F5F5F5` | `#9E9E9E` | `#757575` | Legacy systems |

---

## Connection & Arrow Colors

| Connection Type | Color | Width | Style | Use For |
|-----------------|-------|-------|-------|---------|
| Primary Flow | `#1565C0` | 2px | Solid | Main data/request flow |
| Secondary Flow | `#78909C` | 1.5px | Solid | Supporting flows |
| Async/Event | `#7B1FA2` | 1.5px | Dashed | Event-driven, pub/sub |
| Error Path | `#C62828` | 2px | Dashed | Exception handling |
| External API | `#00796B` | 1.5px | Dotted | Third-party integrations |
| Deprecated | `#9E9E9E` | 1px | Dotted | Legacy connections |

---

## Security & Compliance

| Element | Background | Stroke | Use For |
|---------|------------|--------|---------|
| Security Boundary | `#FCE4EC` | `#AD1457` | Security perimeters |
| Authentication | `#E8EAF6` | `#3949AB` | Auth services, SSO |
| Encryption | `#E0F2F1` | `#00695C` | Encrypted data flows |
| Firewall/WAF | `#FFEBEE` | `#C62828` | Network security |
| Audit/Logging | `#FFF8E1` | `#FF8F00` | Compliance, monitoring |

---

## Semantic Color Scale

### Enterprise Blues (Primary)

- `#E8F4FD` - Background (containers, groups)
- `#BBDEFB` - Light fill (secondary elements)
- `#1565C0` - Stroke (borders, lines)
- `#0D47A1` - Text (labels, headers)
- `#0A3880` - Emphasis (critical labels)

### Enterprise Greens (Success/Active)

- `#E8F5E9` - Background
- `#C8E6C9` - Light fill
- `#2E7D32` - Stroke
- `#1B5E20` - Text
- `#0D3E12` - Emphasis

### Enterprise Oranges (Warning/Attention)

- `#FFF3E0` - Background
- `#FFE0B2` - Light fill
- `#EF6C00` - Stroke
- `#E65100` - Text
- `#BF360C` - Emphasis

### Enterprise Reds (Error/Critical)

- `#FFEBEE` - Background
- `#FFCDD2` - Light fill
- `#C62828` - Stroke
- `#B71C1C` - Text
- `#7F0000` - Emphasis

### Enterprise Purples (Integration/Special)

- `#F3E5F5` - Background
- `#E1BEE7` - Light fill
- `#7B1FA2` - Stroke
- `#4A148C` - Text
- `#2A0A50` - Emphasis

### Enterprise Neutrals

- `#FFFFFF` - Pure white
- `#FAFAFA` - Off-white (canvas)
- `#F5F5F5` - Light gray (backgrounds)
- `#E0E0E0` - Border gray
- `#9E9E9E` - Muted text
- `#616161` - Secondary text
- `#424242` - Primary text
- `#212121` - Headers/emphasis

---

## Best Practices for Enterprise Diagrams

### Color Usage Guidelines

1. **Maximum 4-5 colors per diagram** - Prevents visual overload
2. **Use cloud provider colors** - For services within that ecosystem
3. **Consistent status colors** - Green=healthy, Yellow=warning, Red=error
4. **Gray for neutral/supporting** - Non-critical infrastructure
5. **White text on dark headers** - Minimum 4.5:1 contrast

### Professional Presentation Tips

1. **Avoid pure black** - Use `#212121` or `#424242` instead
2. **No gradients in architecture diagrams** - Keep fills flat
3. **Consistent stroke width** - 1.5px for shapes, 2px for emphasis
4. **White or light canvas** - `#FFFFFF` or `#FAFAFA`
5. **Adequate whitespace** - Don't crowd elements

### Accessibility Requirements

1. **Contrast ratios** - 4.5:1 for normal text, 3:1 for large text
2. **Don't rely on color alone** - Use labels, patterns, icons
3. **Test with colorblind filters** - Ensure diagram is readable
4. **Use consistent iconography** - Official cloud provider icons

---

## Quick Reference Card

| Purpose | Background | Stroke | Text |
|---------|------------|--------|------|
| Primary Service | `#E8F4FD` | `#1565C0` | `#0D47A1` |
| Database | `#E8F5E9` | `#2E7D32` | `#1B5E20` |
| External API | `#F3E5F5` | `#7B1FA2` | `#4A148C` |
| User/Client | `#FFF8E1` | `#F57C00` | `#E65100` |
| Security Zone | `#FFEBEE` | `#C62828` | `#B71C1C` |
| Infrastructure | `#ECEFF1` | `#546E7A` | `#37474F` |
