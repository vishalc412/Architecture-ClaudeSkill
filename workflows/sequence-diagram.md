# Sequence Diagram Workflow

Create interaction diagrams showing how objects/systems communicate over time through message passing.

---

## When to Use

- API request/response flows
- Authentication/authorization flows
- Microservice interactions
- User journey through system
- Protocol implementations
- Error handling flows
- Asynchronous messaging patterns

---

## Intelligent Interaction Analysis

**Before drawing lifelines, THINK like a systems architect.**

### Step 1: Identify Actors and Systems

Ask yourself:

- **Who initiates?** (User, external system, cron job)
- **What systems are involved?** (Frontend, API, Database, External Service)
- **What is the boundary?** (What's inside vs outside your system)

**Actor types:**

- **Human actors:** User, Admin, Customer
- **System actors:** Frontend, Mobile App, CLI
- **Internal services:** API Gateway, Auth Service, Database
- **External services:** Payment Gateway, Email Service, Third-party API

### Step 2: Define the Scenario

Be specific about the use case:

- **Happy path:** Normal successful flow
- **Error path:** What happens when things fail
- **Alternative paths:** Different branches based on conditions

**Scenario format:** "User logs in with valid credentials and receives a JWT token"

### Step 3: Map the Message Flow

For each interaction, determine:

1. **Who sends?** (Source actor/system)
2. **Who receives?** (Target actor/system)
3. **What is sent?** (Message name and parameters)
4. **What is returned?** (Response or acknowledgment)
5. **Is it synchronous or asynchronous?** (Wait for response or fire-and-forget)

**Message types:**

- **Synchronous call:** Solid arrow, wait for response
- **Asynchronous message:** Solid arrow, no wait
- **Return message:** Dashed arrow
- **Self-call:** Loop back to same lifeline

### Step 4: Identify Activation Periods

Activation boxes show when an object is "active" (processing):

- Start when object receives a message
- End when object finishes processing
- Can be nested (object calls another object)

### Step 5: Add Control Flow

Consider:

- **Loops:** Repeated actions (e.g., "for each item")
- **Conditionals:** Branching logic (e.g., "if valid")
- **Parallel execution:** Concurrent operations
- **Error handling:** Try-catch blocks, fallbacks

---

## UML Sequence Diagram Notation

### Lifelines

- Vertical dashed line representing an actor/object over time
- Box at top with actor/object name
- Time flows from top to bottom

### Messages

- **Synchronous:** Solid line with filled arrowhead →
- **Asynchronous:** Solid line with open arrowhead ⇢
- **Return:** Dashed line with open arrowhead ⤺
- **Create:** Dashed line to new lifeline
- **Destroy:** X at end of lifeline

### Activation Boxes

- Thin vertical rectangle on lifeline
- Shows when object is processing
- Can be nested

### Fragments (Optional)

- **alt:** Alternative paths (if-else)
- **opt:** Optional execution (if)
- **loop:** Repeated execution
- **par:** Parallel execution

---

## Process

### 1. Gather Information

Ask the user:

- What is the scenario/use case?
- Who are the actors/systems involved?
- What is the sequence of interactions?
- Are there any error cases to show?

### 2. Plan the Flow

Describe the structure:

- "Actors: User, Frontend, API, Database"
- "Flow: User submits login → Frontend sends credentials → API validates → Database checks → API returns token → Frontend stores token"

### 3. Confirm with User

> "Here's the sequence flow. Does this capture the interaction correctly?"

### 4. Generate Draw.io XML

Use the format from `references/drawio-format.md`.

---

## Layout Rules

### Canvas Setup

- Width: **1000-1400px** (depends on lifeline count)
- Height: **600-1000px** (depends on message count)
- Grid: **10px**

### Lifeline Structure

| Component | Dimensions | Notes |
|-----------|-----------|-------|
| Lifeline box width | 100px | Actor/object name |
| Lifeline box height | 60px | |
| Lifeline spacing | 150-200px | Horizontal gap between lifelines |
| Activation box width | 10px | Thin rectangle |
| Message vertical spacing | 60-80px | Gap between messages |

### Positioning

**Lifeline X positions (200px spacing):**

- Lifeline 1: X = 100
- Lifeline 2: X = 300
- Lifeline 3: X = 500
- Lifeline 4: X = 700
- Lifeline 5: X = 900

**Message Y positions (70px spacing):**

- Message 1: Y = 180
- Message 2: Y = 250
- Message 3: Y = 320
- Message 4: Y = 390
- Message 5: Y = 460

**Lifeline height:** Start at Y = 100, extend to Y = (last message Y + 100)

---

## Color Scheme

### Lifeline Types

| Lifeline Type | Fill Color | Stroke Color | Use For |
|--------------|-----------|--------------|---------|
| **Human Actor** | `#f8cecc` | `#b85450` | Users, admins |
| **Frontend** | `#dae8fc` | `#6c8ebf` | Web, mobile apps |
| **Backend Service** | `#d5e8d4` | `#82b366` | APIs, microservices |
| **Database** | `#e1d5e7` | `#9673a6` | Databases, caches |
| **External Service** | `#fff2cc` | `#d6b656` | Third-party APIs |

### Message Types

| Message Type | Stroke Color | Style | Arrow |
|-------------|--------------|-------|-------|
| **Synchronous call** | `#000000` | Solid | Filled |
| **Asynchronous message** | `#666666` | Solid | Open |
| **Return message** | `#999999` | Dashed | Open |
| **Error/Exception** | `#b85450` | Solid | Filled |

### Activation Boxes

| State | Fill Color | Stroke Color |
|-------|-----------|--------------|
| **Active** | `#f8cecc` | `#b85450` |
| **Processing** | `#fff2cc` | `#d6b656` |

---

## Lifeline Template

```xml
<!-- Lifeline: User -->
<mxCell id="lifeline-user" value="User" style="shape=umlLifeline;perimeter=lifelinePerimeter;whiteSpace=wrap;html=1;container=1;dropTarget=0;collapsible=0;recursiveResize=0;outlineConnect=0;portConstraint=eastwest;newEdgeStyle={&quot;edgeStyle&quot;:&quot;elbowEdgeStyle&quot;,&quot;elbow&quot;:&quot;vertical&quot;,&quot;curved&quot;:0,&quot;rounded&quot;:0};fillColor=#f8cecc;strokeColor=#b85450;fontSize=14;fontStyle=1;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="100" height="500" as="geometry"/>
</mxCell>

<!-- Activation box on User lifeline -->
<mxCell id="activation-user-1" value="" style="html=1;points=[];perimeter=orthogonalPerimeter;outlineConnect=0;targetShapes=umlLifeline;portConstraint=eastwest;newEdgeStyle={&quot;edgeStyle&quot;:&quot;elbowEdgeStyle&quot;,&quot;elbow&quot;:&quot;vertical&quot;,&quot;curved&quot;:0,&quot;rounded&quot;:0};fillColor=#f8cecc;strokeColor=#b85450;" vertex="1" parent="lifeline-user">
  <mxGeometry x="45" y="80" width="10" height="60" as="geometry"/>
</mxCell>
```

**Key properties:**

- `shape=umlLifeline` - Draws the lifeline with dashed line
- `container=1` - Allows activation boxes as children
- `portConstraint=eastwest` - Connectors attach to sides
- Activation box: `x="45"` (centered: 50 - 10/2), `y` relative to lifeline start

---

## Message Templates

### Synchronous Call

```xml
<mxCell id="msg-1" value="login(username, password)" style="html=1;verticalAlign=bottom;endArrow=block;edgeStyle=elbowEdgeStyle;elbow=vertical;curved=0;rounded=0;strokeWidth=2;strokeColor=#000000;fontSize=12;labelBackgroundColor=#ffffff;" edge="1" parent="1" source="lifeline-user" target="lifeline-api">
  <mxGeometry relative="1" as="geometry">
    <mxPoint x="150" y="200" as="sourcePoint"/>
    <mxPoint x="350" y="200" as="targetPoint"/>
  </mxGeometry>
</mxCell>
```

**Properties:**

- `endArrow=block` - Filled arrowhead (synchronous)
- `edgeStyle=elbowEdgeStyle` - Clean routing
- `labelBackgroundColor=#ffffff` - White background for label readability

### Return Message

```xml
<mxCell id="return-1" value="token" style="html=1;verticalAlign=bottom;endArrow=open;dashed=1;endSize=8;edgeStyle=elbowEdgeStyle;elbow=vertical;curved=0;rounded=0;strokeWidth=2;strokeColor=#999999;fontSize=12;labelBackgroundColor=#ffffff;" edge="1" parent="1" source="lifeline-api" target="lifeline-user">
  <mxGeometry relative="1" as="geometry">
    <mxPoint x="350" y="240" as="sourcePoint"/>
    <mxPoint x="150" y="240" as="targetPoint"/>
  </mxGeometry>
</mxCell>
```

**Properties:**

- `endArrow=open` - Open arrowhead
- `dashed=1` - Dashed line (return)
- `strokeColor=#999999` - Gray color

### Asynchronous Message

```xml
<mxCell id="msg-async-1" value="sendEmail(user)" style="html=1;verticalAlign=bottom;endArrow=open;edgeStyle=elbowEdgeStyle;elbow=vertical;curved=0;rounded=0;strokeWidth=2;strokeColor=#666666;fontSize=12;labelBackgroundColor=#ffffff;" edge="1" parent="1" source="lifeline-api" target="lifeline-email">
  <mxGeometry relative="1" as="geometry">
    <mxPoint x="350" y="280" as="sourcePoint"/>
    <mxPoint x="550" y="280" as="targetPoint"/>
  </mxGeometry>
</mxCell>
```

**Properties:**

- `endArrow=open` - Open arrowhead (async)
- No return message needed

### Self-Call

```xml
<mxCell id="msg-self-1" value="validateInput()" style="html=1;verticalAlign=bottom;endArrow=block;edgeStyle=elbowEdgeStyle;elbow=vertical;curved=0;rounded=0;strokeWidth=2;strokeColor=#000000;fontSize=12;labelBackgroundColor=#ffffff;" edge="1" parent="1" source="activation-api-1" target="activation-api-1">
  <mxGeometry relative="1" as="geometry">
    <mxPoint x="365" y="220" as="sourcePoint"/>
    <mxPoint x="365" y="250" as="targetPoint"/>
    <Array as="points">
      <mxPoint x="420" y="220"/>
      <mxPoint x="420" y="250"/>
    </Array>
  </mxGeometry>
</mxCell>
```

**Properties:**

- Source and target are the same activation box
- Uses `points` array to create loop

---

## Common Patterns

### Authentication Flow

```
User → Frontend: Enter credentials
Frontend → API: POST /login {username, password}
API → Database: SELECT user WHERE username = ?
Database → API: User record
API → API: Verify password hash
API → Frontend: JWT token
Frontend → User: Redirect to dashboard
```

**Lifelines:** User, Frontend, API, Database
**Messages:** 7 (3 synchronous calls, 3 returns, 1 self-call)

### Payment Processing

```
User → Frontend: Submit payment
Frontend → API: POST /payment {amount, card}
API → PaymentGateway: Charge card
PaymentGateway → API: Transaction ID
API → Database: INSERT transaction
Database → API: Success
API → EmailService: Send receipt (async)
API → Frontend: Payment confirmed
Frontend → User: Show confirmation
```

**Lifelines:** User, Frontend, API, PaymentGateway, Database, EmailService
**Messages:** 9 (includes async message)

### Microservice Communication

```
Client → APIGateway: GET /orders/123
APIGateway → OrderService: getOrder(123)
OrderService → Database: SELECT order
Database → OrderService: Order data
OrderService → UserService: getUser(order.userId)
UserService → Database: SELECT user
Database → UserService: User data
UserService → OrderService: User details
OrderService → APIGateway: Order with user
APIGateway → Client: JSON response
```

**Lifelines:** Client, APIGateway, OrderService, UserService, Database
**Messages:** 10 (nested service calls)

---

## Advanced Elements

### Alt Fragment (If-Else)

```xml
<!-- Alt fragment container -->
<mxCell id="alt-1" value="alt" style="shape=umlFrame;whiteSpace=wrap;html=1;fillColor=#f5f5f5;strokeColor=#666666;fontSize=12;fontStyle=1;align=left;verticalAlign=top;" vertex="1" parent="1">
  <mxGeometry x="80" y="300" width="640" height="200" as="geometry"/>
</mxCell>

<!-- Condition label -->
<mxCell id="alt-condition-1" value="[valid credentials]" style="text;html=1;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;whiteSpace=wrap;rounded=0;fontSize=11;fontStyle=2;" vertex="1" parent="1">
  <mxGeometry x="90" y="310" width="150" height="20" as="geometry"/>
</mxCell>

<!-- Separator line for else -->
<mxCell id="alt-separator" value="" style="line;strokeWidth=1;fillColor=none;align=left;verticalAlign=middle;spacingTop=-1;spacingLeft=3;spacingRight=3;rotatable=0;labelPosition=right;points=[];portConstraint=eastwest;strokeColor=#666666;dashed=1;" vertex="1" parent="1">
  <mxGeometry x="80" y="400" width="640" height="8" as="geometry"/>
</mxCell>

<!-- Else condition -->
<mxCell id="alt-condition-2" value="[invalid credentials]" style="text;html=1;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;whiteSpace=wrap;rounded=0;fontSize=11;fontStyle=2;" vertex="1" parent="1">
  <mxGeometry x="90" y="410" width="150" height="20" as="geometry"/>
</mxCell>
```

### Loop Fragment

```xml
<mxCell id="loop-1" value="loop" style="shape=umlFrame;whiteSpace=wrap;html=1;fillColor=#f5f5f5;strokeColor=#666666;fontSize=12;fontStyle=1;align=left;verticalAlign=top;" vertex="1" parent="1">
  <mxGeometry x="80" y="300" width="640" height="150" as="geometry"/>
</mxCell>

<mxCell id="loop-condition" value="[for each item in cart]" style="text;html=1;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;whiteSpace=wrap;rounded=0;fontSize=11;fontStyle=2;" vertex="1" parent="1">
  <mxGeometry x="90" y="310" width="180" height="20" as="geometry"/>
</mxCell>
```

---

## Complexity Guidelines

### Simple Sequence (3-4 lifelines, 5-8 messages)

- Single use case
- Linear flow
- Minimal branching

### Medium Sequence (5-6 lifelines, 9-15 messages)

- Multiple services
- Some conditional logic
- Error handling

### Complex Sequence (7+ lifelines, 16+ messages)

- Microservice architecture
- Multiple alt/loop fragments
- Consider splitting into multiple diagrams

**Rule:** If you have more than 20 messages, split into separate scenarios.

---

## Pre-Generation Checklist

Before generating the sequence diagram:

**Lifelines:**

- [ ] All actors/systems identified
- [ ] Lifelines ordered left-to-right by interaction flow
- [ ] Lifeline colors match their type (user, frontend, backend, etc.)
- [ ] Lifeline height accommodates all messages

**Messages:**

- [ ] All interactions mapped
- [ ] Message labels describe the action clearly
- [ ] Synchronous vs asynchronous correctly indicated
- [ ] Return messages included for synchronous calls
- [ ] Message spacing is consistent (60-80px vertical)

**Activation:**

- [ ] Activation boxes show processing periods
- [ ] Nested activations for sub-calls
- [ ] Activation boxes properly aligned with messages

**Layout:**

- [ ] No overlapping messages
- [ ] Labels are readable
- [ ] Time flows clearly top-to-bottom
- [ ] Fragments (alt, loop) properly positioned

---

## Example: User Login Sequence

**Scenario:** User logs in with valid credentials

**Lifelines:**

1. User (actor)
2. Frontend (system)
3. API (backend)
4. Database (storage)

**Flow:**

1. User → Frontend: Enter credentials
2. Frontend → API: POST /login {username, password}
3. API → Database: SELECT user WHERE username = ?
4. Database → API: User record
5. API → API: Verify password hash
6. API → Frontend: JWT token
7. Frontend → User: Redirect to dashboard

**Layout:**

- 4 lifelines, 200px apart
- 7 messages, 70px apart
- Total height: ~600px

---

## Output

Save as: `[feature]-sequence.drawio`

Example: `user-login-sequence.drawio`

---

## Tips

1. **Start with happy path** - Add error cases later
2. **Keep it focused** - One scenario per diagram
3. **Use clear labels** - Include method names and key parameters
4. **Show returns** - Don't forget dashed return arrows
5. **Indicate async** - Use open arrows for fire-and-forget
6. **Add notes** - Explain complex logic in text boxes
7. **Consider timing** - Add time constraints if relevant

---

*Sequence Diagrams - Visualizing system interactions over time*
