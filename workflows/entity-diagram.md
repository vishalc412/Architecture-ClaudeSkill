# Entity-Relationship Diagram (ERD) Workflow

Create database schemas and data models showing entities, attributes, and relationships.

---

## When to Use

- Designing database schemas
- Documenting existing data models
- Planning data architecture
- Showing entity relationships (one-to-one, one-to-many, many-to-many)
- Database normalization discussions

---

## Intelligent Data Modeling Analysis

**Before drawing entities, THINK like a data architect.**

### Step 1: Identify Core Entities

Ask yourself:

- What are the main "things" in this system? (nouns → entities)
- What data needs to be stored about each thing? (attributes)
- Which entities are independent? (strong entities)
- Which depend on others? (weak entities)

**Entity identification checklist:**

- Users/Actors (who uses the system)
- Core business objects (what the system manages)
- Transactions (what actions occur)
- Reference data (lookup tables, categories)

### Step 2: Define Attributes

For each entity, determine:

- **Primary Key** - Unique identifier (usually `id`)
- **Required fields** - Cannot be null
- **Optional fields** - Can be null
- **Data types** - INT, VARCHAR, DATE, BOOLEAN, etc.
- **Constraints** - UNIQUE, NOT NULL, DEFAULT

**Attribute naming conventions:**

- Use snake_case: `user_id`, `created_at`
- Be descriptive: `email_address` not `email`
- Indicate type when helpful: `is_active`, `total_amount`

### Step 3: Identify Relationships

For each pair of entities, ask:

1. **Is there a relationship?** (Do they connect?)
2. **What is the cardinality?**
   - One-to-One (1:1): User ↔ Profile
   - One-to-Many (1:N): User → Posts
   - Many-to-Many (M:N): Students ↔ Courses
3. **What is the relationship name?** (verb: "has", "belongs to", "contains")

**Relationship patterns:**

- **Ownership:** User *has many* Posts
- **Association:** Post *belongs to* Category
- **Junction:** Student *enrolls in* Course (via Enrollment table)

### Step 4: Normalization Check

Verify your design:

- **1NF:** No repeating groups (each cell has one value)
- **2NF:** No partial dependencies (all attributes depend on full primary key)
- **3NF:** No transitive dependencies (non-key attributes don't depend on other non-key attributes)

**Common denormalization decisions:**

- Storing calculated fields for performance
- Duplicating data to avoid joins
- Adding redundant foreign keys

### Step 5: Consider Indexes and Constraints

- **Primary Keys:** Every table needs one
- **Foreign Keys:** Enforce referential integrity
- **Unique Constraints:** Email, username, etc.
- **Indexes:** On frequently queried columns

---

## ERD Notation Styles

### Chen Notation (Classic)

- Entities: Rectangles
- Attributes: Ovals
- Relationships: Diamonds
- Cardinality: 1, N, M labels

### Crow's Foot (Most Popular)

- Entities: Rectangles with attributes listed inside
- Relationships: Lines with symbols
  - One: Single line `|`
  - Many: Crow's foot `<`
  - Optional: Circle `○`
  - Mandatory: Line `|`

**We'll use Crow's Foot notation (industry standard).**

---

## Process

### 1. Gather Information

Ask the user:

- What is the system/domain? (e.g., e-commerce, blog, CRM)
- What are the main entities? (e.g., User, Product, Order)
- What relationships exist?
- Any specific constraints or business rules?

### 2. Plan the Layout

Describe the structure:

- "Entities: User, Post, Comment, Category"
- "Relationships: User has many Posts, Post has many Comments, Post belongs to Category"
- "Key attributes: User (id, email, username), Post (id, title, content, user_id, category_id)"

### 3. Confirm with User

> "Here's the ERD structure. Does this match your data model?"

### 4. Generate Draw.io XML

Use the format from `references/drawio-format.md`.

---

## Layout Rules

### Canvas Setup

- Width: **1200-1600px** (depends on entity count)
- Height: **800-1200px**
- Grid: **10px** (snap to grid for alignment)

### Entity Box Structure

| Component | Dimensions | Notes |
|-----------|-----------|-------|
| Entity box width | 160-200px | Wider for long attribute names |
| Header height | 30px | Entity name |
| Attribute row height | 30px | Each attribute |
| Total height | 30 + (30 × attributes) | Dynamic based on attribute count |

### Spacing

| Element | Spacing |
|---------|---------|
| Horizontal gap between entities | 150-200px |
| Vertical gap between entities | 100-150px |
| Relationship line gap | 10px from entity |

### Positioning Strategy

**Star Layout (1 central entity):**

```
        Entity2
           |
Entity1 - Central - Entity3
           |
        Entity4
```

**Linear Layout (sequential):**

```
Entity1 → Entity2 → Entity3 → Entity4
```

**Hierarchical Layout (parent-child):**

```
        Parent
       /  |  \
   Child1 Child2 Child3
```

---

## Color Scheme

### Entity Types

| Entity Type | Fill Color | Stroke Color | Use For |
|-------------|-----------|--------------|---------|
| **Core/Strong** | `#dae8fc` | `#6c8ebf` | Main business entities |
| **Weak/Dependent** | `#fff2cc` | `#d6b656` | Entities that depend on others |
| **Junction/Bridge** | `#e1d5e7` | `#9673a6` | Many-to-many relationship tables |
| **Reference/Lookup** | `#d5e8d4` | `#82b366` | Static reference data |

### Attribute Styling

| Attribute Type | Font Style | Notes |
|---------------|-----------|-------|
| Primary Key | **Bold** | `id: INT (PK)` |
| Foreign Key | *Italic* | `user_id: INT (FK)` |
| Required | Normal | `email: VARCHAR(255)` |
| Optional | Normal, lighter | `phone: VARCHAR(20)` |

### Relationship Lines

| Relationship | Stroke Color | Stroke Width | Style |
|-------------|--------------|--------------|-------|
| One-to-Many | `#666666` | 2px | Solid |
| One-to-One | `#666666` | 2px | Solid |
| Many-to-Many | `#9673a6` | 2px | Solid |
| Optional | `#999999` | 2px | Dashed |

---

## Entity Template

```xml
<!-- Entity: User -->
<mxCell id="entity-user" value="User" style="swimlane;fontStyle=1;childLayout=stackLayout;horizontal=1;startSize=30;horizontalStack=0;resizeParent=1;resizeParentMax=0;resizeLast=0;collapsible=1;marginBottom=0;whiteSpace=wrap;html=1;fillColor=#dae8fc;strokeColor=#6c8ebf;fontSize=14;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="180" height="150" as="geometry"/>
</mxCell>
<mxCell id="user-attr-1" value="id: INT (PK)" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;spacingLeft=4;spacingRight=4;overflow=hidden;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;rotatable=0;whiteSpace=wrap;html=1;fontStyle=1;fontSize=12;" vertex="1" parent="entity-user">
  <mxGeometry y="30" width="180" height="30" as="geometry"/>
</mxCell>
<mxCell id="user-attr-2" value="username: VARCHAR(50)" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;spacingLeft=4;spacingRight=4;overflow=hidden;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;rotatable=0;whiteSpace=wrap;html=1;fontSize=12;" vertex="1" parent="entity-user">
  <mxGeometry y="60" width="180" height="30" as="geometry"/>
</mxCell>
<mxCell id="user-attr-3" value="email: VARCHAR(255)" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;spacingLeft=4;spacingRight=4;overflow=hidden;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;rotatable=0;whiteSpace=wrap;html=1;fontSize=12;" vertex="1" parent="entity-user">
  <mxGeometry y="90" width="180" height="30" as="geometry"/>
</mxCell>
<mxCell id="user-attr-4" value="created_at: TIMESTAMP" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;spacingLeft=4;spacingRight=4;overflow=hidden;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;rotatable=0;whiteSpace=wrap;html=1;fontSize=12;" vertex="1" parent="entity-user">
  <mxGeometry y="120" width="180" height="30" as="geometry"/>
</mxCell>
```

---

## Relationship Templates

### One-to-Many (User → Posts)

```xml
<mxCell id="rel-user-posts" value="has many" style="edgeStyle=entityRelationEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;startArrow=ERone;startFill=0;endArrow=ERmany;strokeWidth=2;strokeColor=#666666;fontSize=12;labelBackgroundColor=#ffffff;" edge="1" parent="1" source="entity-user" target="entity-post">
  <mxGeometry relative="1" as="geometry"/>
</mxCell>
```

**Cardinality symbols:**

- `startArrow=ERone` + `endArrow=ERmany` = One-to-Many
- Start is "one" side, end is "many" side

### One-to-One (User ↔ Profile)

```xml
<mxCell id="rel-user-profile" value="has one" style="edgeStyle=entityRelationEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;startArrow=ERone;startFill=0;endArrow=ERone;endFill=0;strokeWidth=2;strokeColor=#666666;fontSize=12;labelBackgroundColor=#ffffff;" edge="1" parent="1" source="entity-user" target="entity-profile">
  <mxGeometry relative="1" as="geometry"/>
</mxCell>
```

### Many-to-Many (Students ↔ Courses via Enrollment)

```xml
<!-- Student → Enrollment -->
<mxCell id="rel-student-enrollment" value="enrolls in" style="edgeStyle=entityRelationEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;startArrow=ERone;startFill=0;endArrow=ERmany;strokeWidth=2;strokeColor=#9673a6;fontSize=12;labelBackgroundColor=#ffffff;" edge="1" parent="1" source="entity-student" target="entity-enrollment">
  <mxGeometry relative="1" as="geometry"/>
</mxCell>

<!-- Enrollment → Course -->
<mxCell id="rel-enrollment-course" value="for" style="edgeStyle=entityRelationEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;startArrow=ERmany;startFill=0;endArrow=ERone;strokeWidth=2;strokeColor=#9673a6;fontSize=12;labelBackgroundColor=#ffffff;" edge="1" parent="1" source="entity-enrollment" target="entity-course">
  <mxGeometry relative="1" as="geometry"/>
</mxCell>
```

**Junction table (Enrollment):**

- Contains foreign keys from both entities
- May have additional attributes (enrollment_date, grade, etc.)
- Use purple color scheme

---

## Common Patterns

### User-Content Pattern

```
User (1) ──has many──> Post (N)
Post (1) ──has many──> Comment (N)
Comment (N) ──belongs to──> User (1)
```

**Entities:**

- User: id, username, email
- Post: id, title, content, user_id (FK)
- Comment: id, content, post_id (FK), user_id (FK)

### E-commerce Pattern

```
Customer (1) ──places──> Order (N)
Order (N) ──contains──> OrderItem (N)
OrderItem (N) ──references──> Product (1)
```

**Entities:**

- Customer: id, name, email
- Order: id, customer_id (FK), order_date, total
- OrderItem: id, order_id (FK), product_id (FK), quantity, price
- Product: id, name, price, stock

### Multi-tenancy Pattern

```
Organization (1) ──has──> User (N)
Organization (1) ──owns──> Project (N)
Project (N) ──assigned to──> User (N) [via ProjectMember]
```

**Entities:**

- Organization: id, name
- User: id, organization_id (FK), email
- Project: id, organization_id (FK), name
- ProjectMember: id, project_id (FK), user_id (FK), role

---

## Attribute Guidelines

### Primary Keys

- Always name `id`
- Type: `INT` or `BIGINT` (auto-increment)
- Or `UUID` for distributed systems
- Mark as **(PK)** in diagram

### Foreign Keys

- Name as `{referenced_table}_id`
- Example: `user_id`, `post_id`, `category_id`
- Type: Same as referenced primary key
- Mark as **(FK)** in diagram
- Use italic font style

### Timestamps

- `created_at: TIMESTAMP` - When record was created
- `updated_at: TIMESTAMP` - Last modification
- `deleted_at: TIMESTAMP` - Soft delete (nullable)

### Common Fields

- `is_active: BOOLEAN` - Active/inactive status
- `status: VARCHAR(20)` - Enum-like status
- `type: VARCHAR(50)` - Polymorphic type
- `metadata: JSON` - Flexible additional data

---

## Complexity Guidelines

### Simple ERD (3-5 entities)

- Single domain (blog, todo list)
- Few relationships
- Fits on one screen

### Medium ERD (6-10 entities)

- Multiple related domains
- Some many-to-many relationships
- May need grouping/sections

### Complex ERD (11+ entities)

- Enterprise system
- Multiple modules
- Consider creating separate diagrams per module
- Use color coding for modules

**Rule:** If you have more than 12 entities, split into logical modules.

---

## Pre-Generation Checklist

Before generating the ERD:

**Entities:**

- [ ] All entities identified
- [ ] Primary keys defined for each entity
- [ ] Attributes have appropriate data types
- [ ] Required vs optional fields marked
- [ ] Entities colored by type (core, weak, junction, reference)

**Relationships:**

- [ ] All relationships identified
- [ ] Cardinality determined (1:1, 1:N, M:N)
- [ ] Foreign keys placed correctly
- [ ] Relationship names are clear verbs
- [ ] Many-to-many relationships use junction tables

**Layout:**

- [ ] Entities positioned to minimize line crossings
- [ ] Related entities grouped together
- [ ] Consistent spacing applied
- [ ] Labels are readable

---

## Example: Blog Platform ERD

**Entities:**

1. **User** (core) - id, username, email, password_hash, created_at
2. **Post** (core) - id, user_id (FK), category_id (FK), title, content, published_at
3. **Comment** (core) - id, post_id (FK), user_id (FK), content, created_at
4. **Category** (reference) - id, name, slug
5. **Tag** (reference) - id, name, slug
6. **PostTag** (junction) - id, post_id (FK), tag_id (FK)

**Relationships:**

- User (1) → Post (N): "has many"
- User (1) → Comment (N): "writes"
- Post (1) → Comment (N): "has many"
- Category (1) → Post (N): "contains"
- Post (N) ↔ Tag (N) via PostTag: "tagged with"

**Layout:**

```
    Category
        |
        ↓
User → Post → Comment
        ↓
     PostTag
        ↓
       Tag
```

---

## Output

Save as: `[system-name]-erd.drawio`

Example: `blog-platform-erd.drawio`

---

## Tips

1. **Start with core entities** - Add supporting entities later
2. **Normalize first, denormalize if needed** - Follow 3NF, then optimize
3. **Use consistent naming** - snake_case for attributes, PascalCase for entities
4. **Document constraints** - Add notes for unique constraints, indexes
5. **Show sample data** - Consider adding example values in notes
6. **Version your schema** - Track changes over time

---

*Entity-Relationship Diagrams - The foundation of data architecture*
