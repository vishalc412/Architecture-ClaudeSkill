# Low-Level Architecture Diagram Workflow

Create detailed component design diagrams showing classes, modules, interfaces, and their internal structure.

---

## When to Use

- Detailed component design
- Class diagrams (UML)
- Module structure
- Package/namespace organization
- Interface definitions
- Design patterns implementation
- Code architecture documentation
- Developer onboarding

---

## Intelligent Component Design Analysis

**Before drawing classes, THINK like a software architect.**

### Step 1: Identify the Component Scope

Ask yourself:

- **What component am I designing?** (Service, module, package)
- **What is its responsibility?** (Single Responsibility Principle)
- **What are its boundaries?** (What's inside vs outside)

**Scope examples:**

- **Service:** "Payment Processing Service"
- **Module:** "Authentication Module"
- **Package:** "com.example.orders"
- **Feature:** "User Management"

### Step 2: Define Core Classes/Modules

For each class/module, determine:

- **Name:** Clear, descriptive (PascalCase for classes)
- **Type:** Class, Interface, Abstract Class, Enum
- **Responsibility:** What does it do? (one sentence)
- **Attributes:** What data does it hold?
- **Methods:** What operations does it provide?

**Class identification patterns:**

- **Entities:** Represent domain objects (User, Order, Product)
- **Services:** Business logic (PaymentService, EmailService)
- **Repositories:** Data access (UserRepository, OrderRepository)
- **Controllers:** Request handlers (UserController, OrderController)
- **DTOs:** Data transfer objects (UserDTO, CreateOrderRequest)
- **Utilities:** Helper functions (DateUtils, ValidationUtils)

### Step 3: Map Relationships

For each pair of classes, ask:

1. **Is there a relationship?**
2. **What type?**
   - **Association:** Uses/has a reference to
   - **Inheritance:** Is-a relationship
   - **Implementation:** Implements interface
   - **Composition:** Owns/contains (strong ownership)
   - **Aggregation:** Has-a (weak ownership)
   - **Dependency:** Uses temporarily

**Relationship strength:**

- **Inheritance/Implementation:** Strongest (compile-time)
- **Composition:** Strong (lifecycle dependency)
- **Aggregation:** Medium (shared lifecycle)
- **Association:** Weak (just a reference)
- **Dependency:** Weakest (temporary usage)

### Step 4: Apply Design Patterns

Recognize and document patterns:

- **Creational:** Factory, Builder, Singleton
- **Structural:** Adapter, Decorator, Facade
- **Behavioral:** Strategy, Observer, Command

**Pattern indicators:**

- Multiple implementations of same interface → Strategy/Factory
- Wrapping/enhancing behavior → Decorator
- Simplifying complex subsystem → Facade
- One-to-many notification → Observer

### Step 5: Consider SOLID Principles

Verify your design:

- **S**ingle Responsibility: Each class has one reason to change
- **O**pen/Closed: Open for extension, closed for modification
- **L**iskov Substitution: Subtypes are substitutable
- **I**nterface Segregation: Many specific interfaces > one general
- **D**ependency Inversion: Depend on abstractions, not concretions

---

## UML Class Diagram Notation

### Class Structure

```
┌─────────────────────┐
│   ClassName         │ ← Class name (bold)
├─────────────────────┤
│ - privateField      │ ← Attributes
│ + publicField       │
├─────────────────────┤
│ + publicMethod()    │ ← Methods
│ - privateMethod()   │
└─────────────────────┘
```

### Visibility Modifiers

| Symbol | Visibility | Description |
|--------|-----------|-------------|
| `+` | Public | Accessible from anywhere |
| `-` | Private | Accessible only within class |
| `#` | Protected | Accessible in class and subclasses |
| `~` | Package | Accessible within same package |

### Relationship Types

| Relationship | Line Style | Arrow | Meaning |
|-------------|-----------|-------|---------|
| **Inheritance** | Solid | Hollow triangle | "is-a" |
| **Implementation** | Dashed | Hollow triangle | "implements" |
| **Association** | Solid | Open arrow | "has-a" |
| **Composition** | Solid | Filled diamond | "owns" (strong) |
| **Aggregation** | Solid | Hollow diamond | "has-a" (weak) |
| **Dependency** | Dashed | Open arrow | "uses" |

### Multiplicity

| Notation | Meaning |
|----------|---------|
| `1` | Exactly one |
| `0..1` | Zero or one |
| `*` or `0..*` | Zero or more |
| `1..*` | One or more |
| `n` | Exactly n |

---

## Process

### 1. Gather Information

Ask the user:

- What component/service are you designing?
- What are the main classes/modules?
- What design patterns are used?
- What relationships exist between classes?
- Any specific interfaces or abstract classes?

### 2. Plan the Layout

Describe the structure:

- "Classes: User, UserService, UserRepository, UserDTO"
- "Interfaces: IUserRepository, IAuthService"
- "Relationships: UserService uses UserRepository, UserRepository implements IUserRepository"
- "Pattern: Repository pattern with dependency injection"

### 3. Confirm with User

> "Here's the class structure. Does this match your design?"

### 4. Generate Draw.io XML

Use the format from `references/drawio-format.md`.

---

## Layout Rules

### Canvas Setup

- Width: **1200-1600px**
- Height: **800-1200px**
- Grid: **10px**

### Class Box Structure

| Component | Dimensions | Notes |
|-----------|-----------|-------|
| Class box width | 180-220px | Wider for long method names |
| Class name section | 40px height | Bold, centered |
| Attributes section | 25px per attribute | Left-aligned |
| Methods section | 25px per method | Left-aligned |
| Separator lines | 2px | Between sections |

### Spacing

| Element | Spacing |
|---------|---------|
| Horizontal gap between classes | 150-200px |
| Vertical gap between classes | 100-150px |
| Inheritance hierarchy vertical | 120px |
| Package/namespace padding | 40px |

### Layout Patterns

**Inheritance Hierarchy (Top-Down):**

```
        BaseClass
       /    |    \
  Child1  Child2  Child3
```

**Layered Architecture (Top-Down):**

```
    Controllers
        ↓
    Services
        ↓
  Repositories
        ↓
    Entities
```

**Dependency Injection (Left-Right):**

```
Interface ← Implementation
    ↑
 Consumer
```

---

## Color Scheme

### Class Types

| Class Type | Fill Color | Stroke Color | Use For |
|-----------|-----------|--------------|---------|
| **Interface** | `#fff2cc` | `#d6b656` | Interfaces, contracts |
| **Abstract Class** | `#ffe6cc` | `#d79b00` | Abstract base classes |
| **Concrete Class** | `#dae8fc` | `#6c8ebf` | Regular classes |
| **Entity/Model** | `#d5e8d4` | `#82b366` | Domain entities |
| **DTO** | `#e1d5e7` | `#9673a6` | Data transfer objects |
| **Utility/Helper** | `#f5f5f5` | `#666666` | Static utilities |

### Relationship Lines

| Relationship | Stroke Color | Stroke Width |
|-------------|--------------|--------------|
| Inheritance | `#000000` | 2px |
| Implementation | `#d6b656` | 2px |
| Association | `#666666` | 2px |
| Composition | `#000000` | 2px |
| Dependency | `#999999` | 1px |

---

## Class Template

```xml
<!-- Class: UserService -->
<mxCell id="class-userservice" value="UserService" style="swimlane;fontStyle=1;align=center;verticalAlign=top;childLayout=stackLayout;horizontal=1;startSize=40;horizontalStack=0;resizeParent=1;resizeParentMax=0;resizeLast=0;collapsible=1;marginBottom=0;whiteSpace=wrap;html=1;fillColor=#dae8fc;strokeColor=#6c8ebf;fontSize=14;" vertex="1" parent="1">
  <mxGeometry x="300" y="200" width="200" height="180" as="geometry"/>
</mxCell>

<!-- Attributes section separator -->
<mxCell id="userservice-attrs" value="" style="line;strokeWidth=2;fillColor=none;align=left;verticalAlign=middle;spacingTop=-1;spacingLeft=3;spacingRight=3;rotatable=0;labelPosition=right;points=[];portConstraint=eastwest;strokeColor=#6c8ebf;" vertex="1" parent="class-userservice">
  <mxGeometry y="40" width="200" height="8" as="geometry"/>
</mxCell>

<!-- Attributes -->
<mxCell id="userservice-attr-1" value="- repository: IUserRepository" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;spacingLeft=4;spacingRight=4;overflow=hidden;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;rotatable=0;whiteSpace=wrap;html=1;fontSize=12;" vertex="1" parent="class-userservice">
  <mxGeometry y="48" width="200" height="26" as="geometry"/>
</mxCell>

<mxCell id="userservice-attr-2" value="- logger: ILogger" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;spacingLeft=4;spacingRight=4;overflow=hidden;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;rotatable=0;whiteSpace=wrap;html=1;fontSize=12;" vertex="1" parent="class-userservice">
  <mxGeometry y="74" width="200" height="26" as="geometry"/>
</mxCell>

<!-- Methods section separator -->
<mxCell id="userservice-methods" value="" style="line;strokeWidth=2;fillColor=none;align=left;verticalAlign=middle;spacingTop=-1;spacingLeft=3;spacingRight=3;rotatable=0;labelPosition=right;points=[];portConstraint=eastwest;strokeColor=#6c8ebf;" vertex="1" parent="class-userservice">
  <mxGeometry y="100" width="200" height="8" as="geometry"/>
</mxCell>

<!-- Methods -->
<mxCell id="userservice-method-1" value="+ getUser(id: string): User" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;spacingLeft=4;spacingRight=4;overflow=hidden;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;rotatable=0;whiteSpace=wrap;html=1;fontSize=12;" vertex="1" parent="class-userservice">
  <mxGeometry y="108" width="200" height="26" as="geometry"/>
</mxCell>

<mxCell id="userservice-method-2" value="+ createUser(data: CreateUserDTO): User" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;spacingLeft=4;spacingRight=4;overflow=hidden;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;rotatable=0;whiteSpace=wrap;html=1;fontSize=12;fontStyle=0" vertex="1" parent="class-userservice">
  <mxGeometry y="134" width="200" height="26" as="geometry"/>
</mxCell>

<mxCell id="userservice-method-3" value="+ updateUser(id: string, data: UpdateUserDTO): User" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;spacingLeft=4;spacingRight=4;overflow=hidden;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;rotatable=0;whiteSpace=wrap;html=1;fontSize=12;fontStyle=0" vertex="1" parent="class-userservice">
  <mxGeometry y="160" width="200" height="26" as="geometry"/>
</mxCell>
```

---

## Interface Template

```xml
<!-- Interface: IUserRepository -->
<mxCell id="interface-userrepo" value="&lt;&lt;interface&gt;&gt;&lt;br&gt;&lt;b&gt;IUserRepository&lt;/b&gt;" style="swimlane;fontStyle=0;align=center;verticalAlign=top;childLayout=stackLayout;horizontal=1;startSize=55;horizontalStack=0;resizeParent=1;resizeParentMax=0;resizeLast=0;collapsible=1;marginBottom=0;whiteSpace=wrap;html=1;fillColor=#fff2cc;strokeColor=#d6b656;fontSize=12;" vertex="1" parent="1">
  <mxGeometry x="300" y="100" width="200" height="140" as="geometry"/>
</mxCell>

<!-- Methods separator -->
<mxCell id="userrepo-methods" value="" style="line;strokeWidth=2;fillColor=none;align=left;verticalAlign=middle;spacingTop=-1;spacingLeft=3;spacingRight=3;rotatable=0;labelPosition=right;points=[];portConstraint=eastwest;strokeColor=#d6b656;" vertex="1" parent="interface-userrepo">
  <mxGeometry y="55" width="200" height="8" as="geometry"/>
</mxCell>

<!-- Methods -->
<mxCell id="userrepo-method-1" value="+ findById(id: string): User" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;spacingLeft=4;spacingRight=4;overflow=hidden;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;rotatable=0;whiteSpace=wrap;html=1;fontSize=12;fontStyle=2" vertex="1" parent="interface-userrepo">
  <mxGeometry y="63" width="200" height="26" as="geometry"/>
</mxCell>

<mxCell id="userrepo-method-2" value="+ save(user: User): void" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;spacingLeft=4;spacingRight=4;overflow=hidden;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;rotatable=0;whiteSpace=wrap;html=1;fontSize=12;fontStyle=2" vertex="1" parent="interface-userrepo">
  <mxGeometry y="89" width="200" height="26" as="geometry"/>
</mxCell>

<mxCell id="userrepo-method-3" value="+ delete(id: string): void" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;spacingLeft=4;spacingRight=4;overflow=hidden;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;rotatable=0;whiteSpace=wrap;html=1;fontSize=12;fontStyle=2" vertex="1" parent="interface-userrepo">
  <mxGeometry y="115" width="200" height="26" as="geometry"/>
</mxCell>
```

---

## Relationship Templates

### Inheritance (Extends)

```xml
<mxCell id="rel-inheritance" value="" style="endArrow=block;endSize=16;endFill=0;html=1;rounded=0;strokeWidth=2;strokeColor=#000000;" edge="1" parent="1" source="child-class" target="parent-class">
  <mxGeometry width="160" relative="1" as="geometry">
    <mxPoint x="400" y="400" as="sourcePoint"/>
    <mxPoint x="400" y="300" as="targetPoint"/>
  </mxGeometry>
</mxCell>
```

### Implementation (Implements)

```xml
<mxCell id="rel-implementation" value="" style="endArrow=block;dashed=1;endFill=0;endSize=16;html=1;rounded=0;strokeWidth=2;strokeColor=#d6b656;" edge="1" parent="1" source="concrete-class" target="interface">
  <mxGeometry width="160" relative="1" as="geometry">
    <mxPoint x="400" y="400" as="sourcePoint"/>
    <mxPoint x="400" y="300" as="targetPoint"/>
  </mxGeometry>
</mxCell>
```

### Association (Uses)

```xml
<mxCell id="rel-association" value="uses" style="endArrow=open;html=1;endSize=12;rounded=0;strokeWidth=2;strokeColor=#666666;fontSize=12;labelBackgroundColor=#ffffff;" edge="1" parent="1" source="class-a" target="class-b">
  <mxGeometry width="160" relative="1" as="geometry">
    <mxPoint x="300" y="300" as="sourcePoint"/>
    <mxPoint x="500" y="300" as="targetPoint"/>
  </mxGeometry>
</mxCell>
```

### Composition (Owns)

```xml
<mxCell id="rel-composition" value="" style="endArrow=none;html=1;endSize=12;startArrow=diamond;startSize=14;startFill=1;edgeStyle=orthogonalEdgeStyle;rounded=0;strokeWidth=2;strokeColor=#000000;" edge="1" parent="1" source="owner-class" target="owned-class">
  <mxGeometry width="160" relative="1" as="geometry">
    <mxPoint x="300" y="300" as="sourcePoint"/>
    <mxPoint x="500" y="300" as="targetPoint"/>
  </mxGeometry>
</mxCell>
```

### Aggregation (Has)

```xml
<mxCell id="rel-aggregation" value="" style="endArrow=none;html=1;endSize=12;startArrow=diamond;startSize=14;startFill=0;edgeStyle=orthogonalEdgeStyle;rounded=0;strokeWidth=2;strokeColor=#666666;" edge="1" parent="1" source="container-class" target="contained-class">
  <mxGeometry width="160" relative="1" as="geometry">
    <mxPoint x="300" y="300" as="sourcePoint"/>
    <mxPoint x="500" y="300" as="targetPoint"/>
  </mxGeometry>
</mxCell>
```

### Dependency (Depends On)

```xml
<mxCell id="rel-dependency" value="depends on" style="endArrow=open;html=1;endSize=12;dashed=1;rounded=0;strokeWidth=1;strokeColor=#999999;fontSize=12;labelBackgroundColor=#ffffff;" edge="1" parent="1" source="dependent-class" target="dependency-class">
  <mxGeometry width="160" relative="1" as="geometry">
    <mxPoint x="300" y="300" as="sourcePoint"/>
    <mxPoint x="500" y="300" as="targetPoint"/>
  </mxGeometry>
</mxCell>
```

---

## Common Design Patterns

### 1. Repository Pattern

**Classes:**

- `IUserRepository` (interface)
- `UserRepository` (implementation)
- `UserService` (uses repository)
- `User` (entity)

**Relationships:**

- UserRepository implements IUserRepository
- UserService uses IUserRepository
- UserRepository manages User entities

### 2. Factory Pattern

**Classes:**

- `IPaymentProcessor` (interface)
- `StripeProcessor`, `PayPalProcessor` (implementations)
- `PaymentProcessorFactory` (factory)

**Relationships:**

- Processors implement IPaymentProcessor
- Factory creates IPaymentProcessor instances

### 3. Strategy Pattern

**Classes:**

- `ISortStrategy` (interface)
- `QuickSort`, `MergeSort`, `BubbleSort` (strategies)
- `Sorter` (context)

**Relationships:**

- Strategies implement ISortStrategy
- Sorter uses ISortStrategy

### 4. Observer Pattern

**Classes:**

- `IObserver` (interface)
- `Subject` (observable)
- `ConcreteObserver` (observer)

**Relationships:**

- ConcreteObserver implements IObserver
- Subject has many IObserver
- Subject notifies observers

### 5. Dependency Injection

**Classes:**

- `ILogger` (interface)
- `ConsoleLogger`, `FileLogger` (implementations)
- `UserService` (depends on ILogger)

**Relationships:**

- Loggers implement ILogger
- UserService depends on ILogger (injected)

---

## Layered Architecture Example

### Presentation Layer

- `UserController`
- `OrderController`

### Business Layer

- `UserService`
- `OrderService`
- `IUserRepository` (interface)
- `IOrderRepository` (interface)

### Data Layer

- `UserRepository` (implements IUserRepository)
- `OrderRepository` (implements IOrderRepository)
- `User` (entity)
- `Order` (entity)

**Relationships:**

- Controllers use Services
- Services use Repository interfaces
- Repositories implement interfaces
- Repositories manage Entities

---

## Complexity Guidelines

### Simple Design (3-5 classes)

- Single feature/module
- Few relationships
- One or two patterns

### Medium Design (6-10 classes)

- Multiple related features
- Several interfaces
- Multiple design patterns

### Complex Design (11+ classes)

- Full service/module
- Many interfaces and implementations
- Consider grouping by package/namespace

**Rule:** If you have more than 15 classes, create separate diagrams per package/module.

---

## Pre-Generation Checklist

Before generating the low-level architecture diagram:

**Classes:**

- [ ] All classes identified
- [ ] Visibility modifiers specified (+, -, #)
- [ ] Attributes with types defined
- [ ] Methods with parameters and return types
- [ ] Classes colored by type (interface, abstract, concrete, etc.)

**Relationships:**

- [ ] All relationships identified
- [ ] Correct relationship types (inheritance, implementation, etc.)
- [ ] Multiplicity indicated where relevant
- [ ] Relationship directions are correct

**Design:**

- [ ] SOLID principles followed
- [ ] Design patterns documented
- [ ] Dependencies point to abstractions
- [ ] No circular dependencies

**Layout:**

- [ ] Inheritance hierarchies flow top-to-bottom
- [ ] Dependencies flow left-to-right
- [ ] Related classes grouped together
- [ ] No overlapping elements

---

## Example: User Management Module

**Classes:**

1. **IUserRepository** (interface) - findById, save, delete
2. **UserRepository** (class) - implements IUserRepository
3. **UserService** (class) - uses IUserRepository
4. **UserController** (class) - uses UserService
5. **User** (entity) - id, username, email
6. **CreateUserDTO** (DTO) - username, email, password
7. **UpdateUserDTO** (DTO) - username, email

**Relationships:**

- UserRepository implements IUserRepository
- UserService uses IUserRepository
- UserController uses UserService
- UserRepository manages User
- UserService uses CreateUserDTO, UpdateUserDTO

**Layout:**

```
        UserController
              ↓
        UserService
              ↓
      IUserRepository ← UserRepository
              ↓
            User
```

---

## Output

Save as: `[component-name]-class-diagram.drawio`

Example: `user-management-class-diagram.drawio`

---

## Tips

1. **Start with interfaces** - Define contracts first
2. **Follow naming conventions** - PascalCase for classes, camelCase for methods
3. **Show key methods only** - Don't list every getter/setter
4. **Use stereotypes** - `<<interface>>`, `<<abstract>>`, `<<enum>>`
5. **Group by package** - Use containers for namespaces
6. **Document patterns** - Add notes explaining design decisions
7. **Keep it DRY** - Don't repeat information from high-level diagrams

---

## Complementary Diagrams

Low-level architecture works best with:

- **High-Level Architecture:** System overview
- **Sequence Diagrams:** Method call flows
- **State Diagrams:** Object lifecycle
- **Package Diagrams:** Module dependencies

---

*Low-Level Architecture Diagrams - The detailed blueprint of your code*
