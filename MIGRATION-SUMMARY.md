# Draw.io Diagrams Skill - Migration Summary

## What Changed

I've successfully transformed your Excalidraw skill into a comprehensive **Draw.io Diagrams Skill** with expanded capabilities.

### Before (Excalidraw)

- ✅ Mind Maps
- ✅ Process Flows
- ✅ Swimlanes

### After (Draw.io)

- ✅ Mind Maps (retained)
- ✅ Process Flows (retained)
- ✅ Swimlanes (retained)
- ✨ **Entity-Relationship Diagrams (ERD)** - NEW
- ✨ **Sequence Diagrams** - NEW
- ✨ **High-Level Architecture** - NEW
- ✨ **Low-Level Architecture (Class Diagrams)** - NEW

---

## New Diagram Types

### 1. Entity-Relationship Diagrams (ERD)

**Use for:** Database schema design, data modeling

**Features:**

- Crow's Foot notation (industry standard)
- Entity tables with attributes
- Primary keys (PK) and Foreign keys (FK)
- Relationship types: One-to-One, One-to-Many, Many-to-Many
- Junction tables for M:N relationships
- Color coding by entity type (core, weak, junction, reference)

**Common patterns included:**

- User-Content pattern (blog, social media)
- E-commerce pattern (customers, orders, products)
- Multi-tenancy pattern (organizations, users, projects)

**Example use cases:**

- "Design an ERD for my e-commerce database"
- "Create a data model for a blog platform with users, posts, and comments"
- "Show the database schema for an inventory management system"

---

### 2. Sequence Diagrams

**Use for:** API flows, system interactions, message passing

**Features:**

- UML sequence diagram notation
- Lifelines for actors and systems
- Synchronous and asynchronous messages
- Return messages (dashed arrows)
- Activation boxes (processing periods)
- Self-calls and loops
- Alt fragments (if-else logic)
- Loop fragments (iterations)

**Common patterns included:**

- Authentication flow (login, JWT tokens)
- Payment processing (with external gateway)
- Microservice communication (service-to-service calls)

**Example use cases:**

- "Show the sequence diagram for OAuth 2.0 authentication"
- "Create an API flow for user registration"
- "Visualize the interaction between frontend, API, and database during checkout"

---

### 3. High-Level Architecture

**Use for:** System overview, component relationships, cloud architecture

**Features:**

- Major system components (frontend, backend, database)
- External services and integrations
- Data flow and communication protocols
- Technology stack visualization
- Cloud service indicators (AWS, Azure, GCP)
- System boundaries and containers

**Common patterns included:**

- Three-tier web application
- Microservices with API Gateway
- Event-driven architecture
- Serverless architecture
- CQRS pattern

**Example use cases:**

- "Show the high-level architecture of my video streaming platform"
- "Create an architecture diagram for a microservices e-commerce system"
- "Visualize the cloud infrastructure for my SaaS application"

---

### 4. Low-Level Architecture (Class Diagrams)

**Use for:** Detailed component design, class structure, design patterns

**Features:**

- UML class diagram notation
- Classes with attributes and methods
- Interfaces and abstract classes
- Visibility modifiers (+, -, #, ~)
- Relationship types:
  - Inheritance (is-a)
  - Implementation (implements)
  - Association (uses)
  - Composition (owns)
  - Aggregation (has-a)
  - Dependency (depends on)
- Design pattern documentation

**Common patterns included:**

- Repository pattern
- Factory pattern
- Strategy pattern
- Observer pattern
- Dependency Injection

**Example use cases:**

- "Design the class diagram for a payment processing service"
- "Show the repository pattern implementation for user management"
- "Create a class diagram for the authentication module"

---

## File Structure

```
excalidraw-free/  (you may want to rename this folder to "drawio-diagrams")
├── SKILL.md                              ← Updated main skill file
├── workflows/
│   ├── mind-maps.md                      ← Existing (needs Draw.io conversion)
│   ├── process-flow.md                   ← Existing (needs Draw.io conversion)
│   ├── swimlane.md                       ← Existing (needs Draw.io conversion)
│   ├── entity-diagram.md                 ← NEW
│   ├── sequence-diagram.md               ← NEW
│   ├── high-level-architecture.md        ← NEW
│   └── low-level-architecture.md         ← NEW
└── references/
    ├── drawio-format.md                  ← NEW (replaces json-format.md)
    └── colors.md                         ← Existing (still applicable)
```

---

## Key Differences: Excalidraw vs Draw.io

### File Format

- **Excalidraw:** JSON format (`.excalidraw`)
- **Draw.io:** XML format (`.drawio`)

### Opening Files

- **Excalidraw:** [excalidraw.com](https://excalidraw.com)
- **Draw.io:** [app.diagrams.net](https://app.diagrams.net) or VS Code extension

### Advantages of Draw.io

1. **More professional** - Industry-standard tool
2. **Better for technical diagrams** - ERD, UML, architecture
3. **More shape libraries** - Built-in icons for AWS, Azure, databases, etc.
4. **Better integration** - Confluence, Jira, Google Drive, VS Code
5. **More export options** - PDF, PNG, SVG, HTML
6. **Offline support** - Desktop app available

---

## How to Use the New Skill

### For Entity Diagrams

```
"Design an ERD for a blog platform with users, posts, comments, and tags"
```

Claude will:

1. Identify entities (User, Post, Comment, Tag)
2. Define attributes with data types
3. Map relationships (one-to-many, many-to-many)
4. Create junction tables if needed
5. Generate the `.drawio` file

### For Sequence Diagrams

```
"Show the sequence diagram for user login with JWT authentication"
```

Claude will:

1. Identify actors (User, Frontend, API, Database)
2. Map the message flow
3. Show synchronous calls and returns
4. Add activation boxes
5. Generate the `.drawio` file

### For High-Level Architecture

```
"Create a high-level architecture for an e-commerce platform with microservices"
```

Claude will:

1. Identify major components (Frontend, API Gateway, Services, Databases)
2. Show external integrations (Payment, Email)
3. Map data flow and protocols
4. Group related components
5. Generate the `.drawio` file

### For Low-Level Architecture

```
"Design the class diagram for a user management module with repository pattern"
```

Claude will:

1. Define classes (UserController, UserService, UserRepository)
2. Define interfaces (IUserRepository)
3. Show relationships (implements, uses)
4. Add attributes and methods
5. Generate the `.drawio` file

---

## Next Steps

### 1. Update Existing Workflows (Optional)

The existing workflows (mind-maps.md, process-flow.md, swimlane.md) still reference Excalidraw JSON format. You may want to:

- Convert them to Draw.io XML format
- Or keep them as-is if you want to support both tools

### 2. Test the Skill

Try creating diagrams with Claude:

- "Create an ERD for a todo app"
- "Show the sequence diagram for API authentication"
- "Design the architecture for a chat application"

### 3. Customize

- Add your own color schemes to `colors.md`
- Add company-specific patterns to workflow files
- Create additional workflow files for your specific needs

---

## Workflow Routing

When you ask Claude to create a diagram, it will automatically:

1. **Identify the type** based on keywords:
   - "ERD", "database", "schema" → Entity Diagram
   - "sequence", "API flow", "interaction" → Sequence Diagram
   - "architecture", "system design", "high level" → High-Level Architecture
   - "class diagram", "low level", "detailed design" → Low-Level Architecture
   - "mind map", "brainstorm" → Mind Map
   - "process", "flow", "steps" → Process Flow
   - "swimlane", "who does what" → Swimlane

2. **Load the appropriate workflow** from the workflows folder

3. **Load core references** (drawio-format.md, colors.md)

4. **Generate the diagram** in Draw.io XML format

---

## Tips for Best Results

1. **Be specific** - "ERD for e-commerce" is better than "database diagram"
2. **Mention key entities/components** - Helps Claude understand scope
3. **Specify relationships** - "User has many Posts" guides the structure
4. **Indicate patterns** - "Using repository pattern" helps with design
5. **Ask for iterations** - "Add caching layer" to refine architecture

---

## Examples

### Entity Diagram

```
"Create an ERD for a social media platform with:
- Users (id, username, email, bio)
- Posts (id, user_id, content, created_at)
- Comments (id, post_id, user_id, content)
- Likes (id, post_id, user_id)
- Followers (follower_id, following_id)

Show all relationships including the many-to-many for followers."
```

### Sequence Diagram

```
"Show the sequence diagram for a payment checkout flow:
1. User submits payment form
2. Frontend validates and sends to API
3. API calls Stripe to process payment
4. Stripe returns transaction ID
5. API saves order to database
6. API sends confirmation email (async)
7. Frontend shows success message

Include error handling for failed payments."
```

### High-Level Architecture

```
"Design the high-level architecture for a video streaming platform:
- Web and mobile clients
- CDN for video delivery
- API Gateway
- Microservices: Auth, Video Processing, User Management, Analytics
- PostgreSQL for metadata
- S3 for video storage
- Redis for caching
- Kafka for event streaming

Show the data flow from upload to playback."
```

### Low-Level Architecture

```
"Create a class diagram for an order processing service using:
- Repository pattern for data access
- Service layer for business logic
- DTOs for API contracts

Include:
- OrderService, OrderRepository, IOrderRepository
- Order entity with id, customerId, items, total
- CreateOrderDTO, UpdateOrderDTO
- Show all relationships and dependencies"
```

---

## Troubleshooting

### If Claude generates Excalidraw instead of Draw.io

- Explicitly say "Create a Draw.io diagram"
- Reference the SKILL.md file
- Ensure the skill is properly loaded

### If the diagram is too complex

- Ask Claude to split into multiple diagrams
- Focus on one subsystem at a time
- Use high-level first, then drill down to low-level

### If relationships are unclear

- Ask Claude to add labels to connections
- Request a legend explaining symbols
- Ask for notes explaining complex relationships

---

## Summary

You now have a **comprehensive diagramming skill** that covers:

- ✅ **Process visualization** (mind maps, flows, swimlanes)
- ✅ **Data modeling** (ERD)
- ✅ **Interaction design** (sequence diagrams)
- ✅ **System architecture** (high-level and low-level)

This makes it a complete solution for **software engineering documentation**, from database design to system architecture to detailed class structures.

---

*Ready to create professional diagrams with Claude!*
