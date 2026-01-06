# Draw.io Diagrams Skill for Claude

A comprehensive Claude skill for creating professional diagrams using Draw.io, covering everything from mind maps to complex architecture diagrams.

---

## 🎯 What This Skill Does

This skill enables Claude to generate **7 types of professional diagrams** in Draw.io format and **comprehensive technical documentation**:

1. **Entity-Relationship Diagrams (ERD)** - Database schemas and data models
2. **Sequence Diagrams** - API flows and system interactions
3. **High-Level Architecture** - System overview and component relationships
4. **Low-Level Architecture** - Class diagrams and detailed design
5. **Process Flows** - Step-by-step procedures and decision trees
6. **Swimlanes** - Multi-role processes and handoffs
7. **Mind Maps** - Brainstorming and concept exploration
8. **Documentation** - Technical guides, SADs, and references

---

## 📁 File Structure

```
drawio-diagrams/
├── SKILL.md                              # Main skill definition
├── MIGRATION-SUMMARY.md                  # Detailed migration guide
├── QUICK-REFERENCE.md                    # Quick lookup guide
├── README.md                             # This file
│
├── workflows/                            # Diagram-specific workflows
│   ├── entity-diagram.md                 # ERD creation guide
│   ├── sequence-diagram.md               # Sequence diagram guide
│   ├── high-level-architecture.md        # System architecture guide
│   ├── low-level-architecture.md         # Class diagram guide
│   ├── process-flow.md                   # Process flow guide (legacy)
│   ├── swimlane.md                       # Swimlane guide (legacy)
│   └── mind-maps.md                      # Mind map guide (legacy)
│
└── references/                           # Core references
    ├── drawio-format.md                  # Draw.io XML format reference
    ├── colors.md                         # Color schemes
    └── json-format.md                    # Legacy Excalidraw format
```

---

## 🚀 Quick Start

### 1. Load the Skill

Make sure Claude has access to this directory. The skill will automatically route to the correct diagram type based on your request.

### 2. Create Your First Diagram

Try these examples:

**Entity Diagram:**

```
"Create an ERD for a blog platform with users, posts, comments, and tags"
```

**Sequence Diagram:**

```
"Show the sequence diagram for user login with JWT authentication"
```

**Architecture Diagram:**

```
"Design the high-level architecture for an e-commerce microservices system"
```

**Class Diagram:**

```
"Create a class diagram for a payment service using repository pattern"
```

### 3. Open the Generated File

1. Go to [app.diagrams.net](https://app.diagrams.net)
2. Click "Open Existing Diagram"
3. Select the `.drawio` file Claude created

---

## 📊 Diagram Types

### Entity-Relationship Diagrams (ERD)

**When to use:**

- Designing database schemas
- Documenting data models
- Planning data architecture

**Features:**

- Crow's Foot notation
- Primary and foreign keys
- One-to-One, One-to-Many, Many-to-Many relationships
- Junction tables for M:N relationships
- Color-coded entity types

**Example prompt:**

```
"Design an ERD for an e-commerce system with customers, orders, products, and inventory"
```

---

### Sequence Diagrams

**When to use:**

- API request/response flows
- Authentication flows
- Microservice interactions
- Time-based system behavior

**Features:**

- UML sequence notation
- Lifelines for actors and systems
- Synchronous and asynchronous messages
- Activation boxes
- Alt/Loop fragments

**Example prompt:**

```
"Create a sequence diagram for OAuth 2.0 authorization code flow"
```

---

### High-Level Architecture

**When to use:**

- System design documentation
- Architecture presentations
- Cloud infrastructure overview
- Stakeholder communication

**Features:**

- Major system components
- Data flow visualization
- Technology stack indicators
- External service integrations
- Common patterns (microservices, event-driven, etc.)

**Example prompt:**

```
"Show the high-level architecture for a video streaming platform using AWS"
```

---

### Low-Level Architecture (Class Diagrams)

**When to use:**

- Detailed component design
- Code structure documentation
- Design pattern implementation
- Developer onboarding

**Features:**

- UML class notation
- Attributes and methods
- Interfaces and abstract classes
- Relationship types (inheritance, composition, etc.)
- Design pattern documentation

**Example prompt:**

```
"Design a class diagram for an order processing service with repository pattern"
```

---

### Process Flows

**When to use:**

- Step-by-step procedures
- Decision trees
- SOPs and workflows

**Features:**

- Start/end nodes
- Process steps
- Decision diamonds
- Flow arrows

**Example prompt:**

```
"Create a process flow for customer complaint handling"
```

---

### Swimlanes

**When to use:**

- Multi-role processes
- Cross-functional workflows
- Responsibility mapping

**Features:**

- Multiple lanes for different actors
- Cross-lane handoffs
- Process phases
- Clear ownership

**Example prompt:**

```
"Show a swimlane diagram for the hiring process with recruiter, hiring manager, and candidate"
```

---

### Mind Maps

**When to use:**

- Brainstorming
- Concept exploration
- Topic organization

**Features:**

- Central topic
- Radial branches
- Hierarchical structure
- Color coding

**Example prompt:**

```
"Create a mind map for planning a mobile app launch"
```

---

## 🎨 Color Schemes

### Entity Diagrams

- **Blue:** Core entities (User, Product)
- **Yellow:** Weak/dependent entities
- **Purple:** Junction tables (many-to-many)
- **Green:** Reference data (Category, Status)

### Sequence Diagrams

- **Red:** Human actors
- **Blue:** Frontend applications
- **Green:** Backend services
- **Purple:** Databases
- **Yellow:** External services

### Architecture Diagrams

- **Blue:** Frontend components
- **Green:** Backend services
- **Purple:** Databases
- **Yellow:** Caches/Queues
- **Orange:** External services
- **Gray:** Infrastructure

---

## 📝 Best Practices

### General

1. **Be specific** - Provide clear requirements and entities
2. **Start simple** - Add complexity iteratively
3. **Use consistent naming** - Follow conventions for your domain
4. **Add labels** - Explain relationships and flows
5. **Group related items** - Use containers and boundaries

### Entity Diagrams

- Follow normalization principles (3NF)
- Use descriptive attribute names
- Indicate primary and foreign keys
- Show cardinality on relationships

### Sequence Diagrams

- Focus on one scenario per diagram
- Show return messages for synchronous calls
- Use activation boxes to show processing
- Add error handling paths

### Architecture Diagrams

- Layer your components logically
- Show technology choices where relevant
- Indicate protocols and data flow
- Highlight external dependencies

### Class Diagrams

- Follow SOLID principles
- Show key methods only (not every getter/setter)
- Use interfaces for abstraction
- Document design patterns used

---

## 🔧 Advanced Usage

### Splitting Complex Diagrams

If your diagram becomes too complex:

```
"Split the architecture into separate diagrams for frontend, backend, and data layers"
```

### Adding Details

To enhance an existing diagram:

```
"Add a caching layer using Redis"
"Show error handling in the sequence diagram"
"Include the email notification service"
```

### Showing Alternatives

To explore different approaches:

```
"Show both monolithic and microservices architecture options"
"Compare repository pattern vs active record pattern"
```

---

## 📚 Documentation

- **SKILL.md** - Main skill definition and routing logic
- **MIGRATION-SUMMARY.md** - Detailed guide on what changed from Excalidraw
- **QUICK-REFERENCE.md** - Fast lookup for common tasks
- **workflows/*.md** - Detailed guides for each diagram type
- **references/drawio-format.md** - Draw.io XML format reference
- **references/colors.md** - Color palette definitions

---

## 🔄 Migration from Excalidraw

If you're coming from the Excalidraw skill:

**What's the same:**

- Mind maps, process flows, and swimlanes are still supported
- Same workflow-based approach
- Same intelligent analysis before generation

**What's new:**

- 4 new diagram types (ERD, Sequence, Architecture)
- Draw.io XML format instead of Excalidraw JSON
- More professional and industry-standard
- Better integration with tools (Confluence, VS Code, etc.)

**What changed:**

- File format: `.drawio` instead of `.excalidraw`
- Opening tool: app.diagrams.net instead of excalidraw.com
- Reference file: drawio-format.md instead of json-format.md

See **MIGRATION-SUMMARY.md** for full details.

---

## 🛠️ Troubleshooting

### Diagram too complex

→ Ask Claude to split into multiple diagrams or focus on a subsystem

### Unclear relationships

→ Request labels on connections and a legend

### Wrong diagram type

→ Explicitly specify: "Create a Draw.io ERD for..."

### Need modifications

→ "Add [component]", "Show [relationship]", "Remove [element]"

### Can't open file

→ Ensure you're using app.diagrams.net or the Draw.io desktop app

---

## 🎓 Learning Resources

### Draw.io Documentation

- [Draw.io User Manual](https://www.diagrams.net/doc/)
- [Draw.io Blog](https://www.diagrams.net/blog)

### Diagram Standards

- [UML Specification](https://www.omg.org/spec/UML/)
- [Crow's Foot Notation](https://www.vertabelo.com/blog/crow-s-foot-notation/)
- [C4 Model](https://c4model.com/) for architecture diagrams

### Design Patterns

- [Refactoring Guru](https://refactoring.guru/design-patterns)
- [Source Making](https://sourcemaking.com/design_patterns)

---

## 🤝 Contributing

To extend this skill:

1. **Add new diagram types** - Create a new workflow file in `workflows/`
2. **Enhance existing workflows** - Add patterns, examples, or templates
3. **Update color schemes** - Modify `references/colors.md`
4. **Add templates** - Include reusable XML snippets in workflow files

---

## 📄 License

This skill is provided as-is for use with Claude. Feel free to modify and extend for your needs.

---

## 🙏 Credits

- Original Excalidraw skill by Rashid
- Enhanced and expanded for Draw.io with comprehensive architecture support
- Built for Claude by the Anthropic community

---

## 📞 Support

For issues or questions:

1. Check the **QUICK-REFERENCE.md** for common tasks
2. Review the **MIGRATION-SUMMARY.md** for detailed explanations
3. Consult the specific workflow file for your diagram type
4. Ask Claude to explain or modify the diagram

---

**Ready to create professional diagrams with Claude!** 🚀

Start with: `"Create a [diagram type] for [your use case]"`
# Architecture-ClaudeSkill
