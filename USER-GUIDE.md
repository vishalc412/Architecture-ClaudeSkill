# Draw.io Diagrams Skill - User Guide

A step-by-step guide to creating professional diagrams with Claude.

---

## Table of Contents

1. [Getting Started](#getting-started)
2. [Creating Entity Diagrams (ERD)](#creating-entity-diagrams-erd)
3. [Creating Sequence Diagrams](#creating-sequence-diagrams)
4. [Creating High-Level Architecture Diagrams](#creating-high-level-architecture-diagrams)
5. [Creating Low-Level Architecture Diagrams](#creating-low-level-architecture-diagrams)
6. [Creating Process Flow Diagrams](#creating-process-flow-diagrams)
7. [Creating Swimlane Diagrams](#creating-swimlane-diagrams)
8. [Creating Mind Maps](#creating-mind-maps)
9. [Tips & Tricks](#tips--tricks)
10. [Troubleshooting](#troubleshooting)

---

## Getting Started

### Prerequisites

1. **Claude** - Access to Claude with this skill loaded
2. **Draw.io** - One of these options:
   - Web: [app.diagrams.net](https://app.diagrams.net)
   - Desktop: [Download](https://www.diagrams.net/)
   - VS Code: Install "Draw.io Integration" extension

### How It Works

1. **You describe** what you want to visualize
2. **Claude identifies** the best diagram type
3. **Claude generates** a `.drawio` file
4. **You open** the file in Draw.io to view/edit

### Quick Command Format

```
"Create a [diagram type] for [your use case]"
```

**Examples:**

- "Create an ERD for an e-commerce database"
- "Create a sequence diagram for user login"
- "Create an architecture diagram for a chat application"

---

## Creating Entity Diagrams (ERD)

### What is an ERD?

Entity-Relationship Diagrams show **database structure** - tables, columns, and relationships.

### When to Use

- Designing a new database
- Documenting existing data models
- Planning data migrations
- Discussing schema with team

### How to Request

**Basic request:**

```
"Create an ERD for a blog platform"
```

**Detailed request (recommended):**

```
"Create an ERD for a blog platform with:
- Users (id, username, email, password_hash, created_at)
- Posts (id, user_id, title, content, published_at)
- Comments (id, post_id, user_id, content, created_at)
- Tags (id, name, slug)
- A many-to-many relationship between Posts and Tags"
```

### What Claude Will Generate

- **Entity boxes** with table names and columns
- **Primary keys** marked as (PK)
- **Foreign keys** marked as (FK)
- **Relationships** with cardinality (1:N, M:N)
- **Junction tables** for many-to-many relationships

### Example Prompts

**E-commerce:**

```
"Design an ERD for an e-commerce platform with customers, orders, products, and inventory tracking"
```

**Social Media:**

```
"Create a data model for a social media app with users, posts, likes, comments, and followers"
```

**SaaS Multi-tenant:**

```
"Design a database schema for a multi-tenant SaaS with organizations, users, projects, and permissions"
```

### Understanding the Output

| Symbol | Meaning |
|--------|---------|
| Blue entities | Core/main tables |
| Yellow entities | Dependent tables |
| Purple entities | Junction tables (M:N) |
| Green entities | Reference/lookup tables |
| `───<` | One-to-Many (1:N) |
| `>───<` | Many-to-Many (M:N) |

---

## Creating Sequence Diagrams

### What is a Sequence Diagram?

Sequence diagrams show **interactions over time** - who talks to whom and in what order.

### When to Use

- API documentation
- Authentication flows
- Microservice interactions
- Debugging complex flows
- Onboarding new developers

### How to Request

**Basic request:**

```
"Create a sequence diagram for user login"
```

**Detailed request (recommended):**

```
"Create a sequence diagram for user login with JWT:
1. User enters credentials on frontend
2. Frontend sends POST /login to API
3. API validates credentials with database
4. Database returns user record
5. API generates JWT token
6. API returns token to frontend
7. Frontend stores token and redirects to dashboard

Include error handling for invalid credentials."
```

### What Claude Will Generate

- **Lifelines** for each actor/system
- **Solid arrows** for synchronous calls
- **Dashed arrows** for return messages
- **Activation boxes** showing processing time
- **Alt fragments** for conditional logic

### Example Prompts

**OAuth Authentication:**

```
"Show the sequence diagram for OAuth 2.0 authorization code flow with a third-party provider"
```

**Payment Processing:**

```
"Create a sequence diagram for checkout:
- User submits payment
- API calls Stripe
- On success, save order to database
- Send confirmation email asynchronously
- Return success to user"
```

**Microservice Communication:**

```
"Show the interaction between API Gateway, Order Service, Inventory Service, and Payment Service when processing an order"
```

### Understanding the Output

| Element | Meaning |
|---------|---------|
| Boxes at top | Actors/Systems |
| Vertical dashed lines | Lifelines (time) |
| Solid arrows (→) | Synchronous calls |
| Dashed arrows (← --) | Return messages |
| Thin rectangles | Activation (processing) |
| [alt] box | Conditional branching |

---

## Creating High-Level Architecture Diagrams

### What is a High-Level Architecture Diagram?

Shows the **big picture** of your system - major components and how they connect.

### When to Use

- System design presentations
- Architecture documentation
- Cloud infrastructure planning
- Stakeholder communication
- New team member onboarding

### How to Request

**Basic request:**

```
"Create a high-level architecture for an e-commerce platform"
```

**Detailed request (recommended):**

```
"Design the high-level architecture for a video streaming platform:

Components:
- Web and mobile clients
- CDN for video delivery
- API Gateway (Kong)
- Microservices: Auth, Video Processing, User Management, Recommendations
- PostgreSQL for metadata
- MongoDB for user activity
- S3 for video storage
- Redis for caching
- Kafka for event streaming

Show data flow from upload to playback."
```

### What Claude Will Generate

- **Component boxes** for each major system part
- **Containers/boundaries** grouping related components
- **Arrows** showing data flow and communication
- **Labels** indicating protocols (HTTP, WebSocket, etc.)
- **External services** clearly marked

### Example Prompts

**Microservices:**

```
"Show the architecture for a ride-sharing app with:
- Mobile apps (iOS, Android)
- API Gateway
- Services: Users, Rides, Payments, Notifications, Location
- Databases per service
- Message queue for async communication"
```

**Serverless:**

```
"Design a serverless architecture on AWS for a file processing pipeline with S3, Lambda, DynamoDB, and SQS"
```

**Real-time Application:**

```
"Create an architecture for a real-time chat application with WebSocket, message queue, and push notifications"
```

### Understanding the Output

| Color | Component Type |
|-------|---------------|
| Red | Users/Actors |
| Blue | Frontend apps |
| Green | Backend services |
| Purple | Databases |
| Yellow | Caches/Queues |
| Orange | External services |
| Gray | Infrastructure |

---

## Creating Low-Level Architecture Diagrams

### What is a Low-Level Architecture Diagram?

Shows **detailed code structure** - classes, interfaces, methods, and relationships.

### When to Use

- Detailed design documentation
- Design pattern implementation
- Code review discussions
- Technical specifications
- Refactoring planning

### How to Request

**Basic request:**

```
"Create a class diagram for a user management service"
```

**Detailed request (recommended):**

```
"Design a class diagram for an order processing service using repository pattern:

Classes:
- OrderController (handles HTTP requests)
- OrderService (business logic)
- IOrderRepository (interface)
- OrderRepository (implementation)
- Order (entity with id, customerId, items, total, status)
- OrderItem (entity with productId, quantity, price)
- CreateOrderDTO, UpdateOrderDTO

Show all relationships:
- Controller uses Service
- Service uses IOrderRepository
- OrderRepository implements IOrderRepository
- Order has many OrderItems (composition)"
```

### What Claude Will Generate

- **Class boxes** with name, attributes, methods
- **Interface boxes** with stereotype `<<interface>>`
- **Visibility symbols** (+public, -private, #protected)
- **Relationships** (inheritance, implementation, association, composition)

### Example Prompts

**Repository Pattern:**

```
"Design a class diagram for user management with UserController, UserService, IUserRepository, UserRepository, and User entity"
```

**Factory Pattern:**

```
"Create a class diagram showing factory pattern for creating different payment processors (Stripe, PayPal, Square)"
```

**Strategy Pattern:**

```
"Show a class diagram with strategy pattern for different sorting algorithms"
```

### Understanding the Output

| Symbol | Meaning |
|--------|---------|
| `+` | Public |
| `-` | Private |
| `#` | Protected |
| Hollow arrow (→) | Inheritance |
| Dashed hollow arrow | Implementation |
| Filled diamond (♦→) | Composition |
| Hollow diamond (◇→) | Aggregation |
| Simple arrow | Association |

---

## Creating Process Flow Diagrams

### What is a Process Flow Diagram?

Shows **step-by-step procedures** with decisions and outcomes.

### When to Use

- Standard Operating Procedures (SOPs)
- Business processes
- Decision trees
- Workflow documentation

### How to Request

**Basic request:**

```
"Create a process flow for order fulfillment"
```

**Detailed request:**

```
"Create a process flow for handling customer returns:
1. Customer initiates return
2. Check if within return window
3. If yes, generate return label
4. Customer ships item
5. Warehouse receives item
6. Inspect item condition
7. If acceptable, process refund
8. If not acceptable, notify customer"
```

### Example Prompts

```
"Create a flowchart for employee onboarding process"
"Show the decision flow for loan approval"
"Map the bug triage process for our development team"
```

---

## Creating Swimlane Diagrams

### What is a Swimlane Diagram?

Shows **who does what** in a process - responsibilities across roles.

### When to Use

- Cross-functional processes
- Handoff documentation
- Responsibility mapping
- Team coordination

### How to Request

**Basic request:**

```
"Create a swimlane for the hiring process"
```

**Detailed request:**

```
"Create a swimlane diagram for content publishing:

Roles: Writer, Editor, Legal, Publisher

Flow:
1. Writer drafts article
2. Editor reviews and provides feedback
3. Writer revises (loop until approved)
4. Legal reviews for compliance
5. Publisher schedules and publishes
6. Publisher notifies stakeholders"
```

### Example Prompts

```
"Show a swimlane for customer support escalation with Agent, Supervisor, and Engineering"
"Create a swimlane for purchase approval with Requester, Manager, and Finance"
"Map the code review process with Developer, Reviewer, and QA"
```

---

## Creating Mind Maps

### What is a Mind Map?

Shows **ideas branching from a central topic** - great for brainstorming.

### When to Use

- Brainstorming sessions
- Planning projects
- Organizing thoughts
- Book/concept summaries

### How to Request

**Basic request:**

```
"Create a mind map for mobile app features"
```

**Detailed request:**

```
"Create a mind map for planning a product launch:

Central topic: Product Launch

Branches:
- Marketing (social media, PR, ads, influencers)
- Development (features, testing, deployment)
- Sales (pricing, channels, training)
- Operations (support, documentation, training)"
```

### Example Prompts

```
"Create a mind map for the key concepts in Domain-Driven Design"
"Map out the features for a fitness tracking app"
"Brainstorm content ideas for a tech blog"
```

---

## Tips & Tricks

### 1. Be Specific

❌ Bad: "Create a database diagram"
✅ Good: "Create an ERD for a blog with users, posts, comments, and tags"

### 2. List Key Elements

❌ Bad: "Show the architecture"
✅ Good: "Show the architecture with: React frontend, Node.js API, PostgreSQL database, Redis cache"

### 3. Specify Relationships

❌ Bad: "Users and orders"
✅ Good: "Users can have many orders, each order belongs to one user"

### 4. Iterate

Start with a basic diagram, then refine:

1. "Create an ERD for e-commerce"
2. "Add an inventory tracking table"
3. "Show the relationship between products and suppliers"

### 5. Ask for Alternatives

"Show me two approaches: monolithic vs microservices architecture"

### 6. Request Specific Patterns

"Use repository pattern for data access"
"Implement with factory pattern"
"Show event-driven architecture"

### 7. Include Error Cases

"Show the sequence diagram for login, including failed authentication"

---

## Troubleshooting

### Issue: Diagram is too complex

**Solution:** Ask Claude to split it:

```
"This is too complex. Can you split it into:
1. Frontend architecture
2. Backend services
3. Data layer"
```

### Issue: Missing relationships

**Solution:** Ask Claude to add them:

```
"Add the relationship between Orders and Products"
"Show how UserService depends on IUserRepository"
```

### Issue: Wrong diagram type

**Solution:** Specify explicitly:

```
"Create a Draw.io ERD (not a class diagram) for..."
```

### Issue: Need more detail

**Solution:** Ask for enhancement:

```
"Add data types to all attributes"
"Include the method parameters"
"Show the HTTP verbs on API calls"
```

### Issue: Can't open the file

**Solution:**

1. Ensure file has `.drawio` extension
2. Use [app.diagrams.net](https://app.diagrams.net)
3. Try the desktop app if web doesn't work

### Issue: Diagram doesn't match requirements

**Solution:** Provide corrections:

```
"The User entity should have an email field"
"The API should call the cache before the database"
"Remove the direct connection between frontend and database"
```

---

## Command Reference

### Entity Diagrams (ERD)

```
"Create an ERD for [system] with [entities]"
"Design a database schema for [feature]"
"Show the data model for [domain]"
```

### Sequence Diagrams

```
"Create a sequence diagram for [use case]"
"Show the API flow for [feature]"
"Visualize the interaction between [systems]"
```

### High-Level Architecture

```
"Design the architecture for [system]"
"Show the high-level design for [application]"
"Create a system diagram for [platform]"
```

### Low-Level Architecture

```
"Create a class diagram for [component]"
"Design the detailed architecture for [service]"
"Show the class structure for [module]"
```

### Process Flows

```
"Create a process flow for [procedure]"
"Show the flowchart for [workflow]"
"Map the steps for [process]"
```

### Swimlanes

```
"Create a swimlane for [process] with [roles]"
"Show who does what in [workflow]"
"Map responsibilities for [procedure]"
```

### Mind Maps

```
"Create a mind map for [topic]"
"Brainstorm ideas for [subject]"
"Map out [concept]"
```

---

## Output Files

All diagrams are saved as `.drawio` files with descriptive names:

| Diagram Type | File Naming |
|-------------|-------------|
| ERD | `[system]-erd.drawio` |
| Sequence | `[feature]-sequence.drawio` |
| Architecture | `[system]-architecture.drawio` |
| Class Diagram | `[component]-class-diagram.drawio` |
| Process Flow | `[process]-flow.drawio` |
| Swimlane | `[process]-swimlane.drawio` |
| Mind Map | `[topic]-mindmap.drawio` |

---

## Opening Your Diagram

### Option 1: Web (Easiest)

1. Go to [app.diagrams.net](https://app.diagrams.net)
2. Click "Open Existing Diagram"
3. Select your `.drawio` file

### Option 2: VS Code

1. Install "Draw.io Integration" extension
2. Open the `.drawio` file directly

### Option 3: Desktop App

1. Download from [diagrams.net](https://www.diagrams.net/)
2. Open the file with the app

### Option 4: Confluence/Jira

1. Upload the `.drawio` file
2. Use the built-in Draw.io integration to view

---

## Exporting Your Diagram

Once open in Draw.io, you can export to:

- **PNG** - For presentations and documents
- **SVG** - For web and scalable graphics
- **PDF** - For printing and sharing
- **HTML** - For interactive web viewing

**How to export:**

1. File → Export as → [format]
2. Choose quality/options
3. Download

---

## Quick Start Checklist

- [ ] Know what you want to visualize
- [ ] Choose the right diagram type
- [ ] List the key elements/entities
- [ ] Specify relationships/connections
- [ ] Ask Claude to generate
- [ ] Open in Draw.io
- [ ] Refine if needed

---

**You're ready to create professional diagrams with Claude!** 🚀

Start with: `"Create a [diagram type] for [your use case]"`
