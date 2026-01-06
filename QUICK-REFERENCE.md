# Draw.io Diagrams - Quick Reference

## Diagram Type Selection

| I need to... | Use this diagram | Example |
|-------------|------------------|---------|
| Design a database schema | **Entity Diagram (ERD)** | Blog with users, posts, comments |
| Show API request/response flow | **Sequence Diagram** | User login with JWT |
| Visualize system components | **High-Level Architecture** | Microservices e-commerce |
| Design class structure | **Low-Level Architecture** | Payment service classes |
| Map a multi-step process | **Process Flow** | Order fulfillment |
| Show who does what | **Swimlane** | Customer onboarding |
| Brainstorm ideas | **Mind Map** | Product features |

---

## Quick Commands

### Entity Diagrams

```
"Create an ERD for [domain] with [entities]"
"Design a database schema for [system]"
"Show the data model for [feature]"
```

### Sequence Diagrams

```
"Show the sequence diagram for [feature]"
"Create an API flow for [action]"
"Visualize the interaction for [use case]"
```

### Architecture Diagrams

```
"Design the high-level architecture for [system]"
"Show the system design for [application]"
"Create the class diagram for [component]"
```

---

## Common Patterns

### ERD Patterns

- **User-Content:** User → Posts → Comments
- **E-commerce:** Customer → Order → OrderItem → Product
- **Multi-tenancy:** Organization → Users, Projects

### Sequence Patterns

- **Authentication:** User → Frontend → API → Database
- **Payment:** User → API → PaymentGateway → Database
- **Microservices:** Client → Gateway → Services → Database

### Architecture Patterns

- **Three-Tier:** Presentation → Business → Data
- **Microservices:** API Gateway → Services → Databases
- **Event-Driven:** Producer → Queue → Consumers

---

## Color Coding

### Entity Diagrams

- 🔵 Blue: Core entities (User, Product)
- 🟡 Yellow: Weak entities (dependent)
- 🟣 Purple: Junction tables (many-to-many)
- 🟢 Green: Reference data (Category, Tag)

### Sequence Diagrams

- 🔴 Red: Human actors (User, Admin)
- 🔵 Blue: Frontend (Web, Mobile)
- 🟢 Green: Backend services (API)
- 🟣 Purple: Databases
- 🟡 Yellow: External services

### Architecture Diagrams

- 🔵 Blue: Frontend components
- 🟢 Green: Backend services
- 🟣 Purple: Databases
- 🟡 Yellow: Caches/Queues
- 🟠 Orange: External services

---

## Relationship Types

### ERD Relationships

- **One-to-Many (1:N):** User has many Posts
- **One-to-One (1:1):** User has one Profile
- **Many-to-Many (M:N):** Students ↔ Courses (via Enrollment)

### Class Diagram Relationships

- **Inheritance:** Child extends Parent
- **Implementation:** Class implements Interface
- **Association:** Class uses another Class
- **Composition:** Class owns another Class
- **Dependency:** Class depends on another Class

---

## File Naming

- ERD: `[system]-erd.drawio`
- Sequence: `[feature]-sequence.drawio`
- Architecture: `[system]-architecture.drawio`
- Class Diagram: `[component]-class-diagram.drawio`
- Process Flow: `[process]-flow.drawio`
- Swimlane: `[process]-swimlane.drawio`
- Mind Map: `[topic]-mindmap.drawio`

---

## Opening Draw.io Files

1. **Online:** [app.diagrams.net](https://app.diagrams.net)
2. **Desktop:** Download from [diagrams.net](https://www.diagrams.net/)
3. **VS Code:** Install "Draw.io Integration" extension
4. **Confluence/Jira:** Built-in integration

---

## Tips

1. **Start simple** - Add complexity iteratively
2. **Use consistent naming** - PascalCase for classes, snake_case for DB
3. **Add labels** - Explain connections and relationships
4. **Group related items** - Use containers/boundaries
5. **Follow standards** - UML for classes, Crow's Foot for ERD
6. **Keep it focused** - One diagram per concern
7. **Version your diagrams** - Track changes over time

---

## Troubleshooting

**Diagram too complex?**
→ Split into multiple diagrams (e.g., per module)

**Unclear relationships?**
→ Ask for labels and a legend

**Wrong diagram type?**
→ Specify explicitly: "Create a Draw.io ERD for..."

**Need modifications?**
→ "Add [component]" or "Show [relationship]"

---

*Quick reference for Draw.io diagram creation with Claude*
