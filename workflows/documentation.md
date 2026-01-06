# Documentation Workflow

Create professional technical documentation to accompany your diagrams.

---

## When to Use

- When the user asks for "documentation", "guide", "explanation", or "readme"
- To provide context for a diagram (architecture, sequence, etc.)
- To document design decisions (ADR)
- To create a handbook or SOP based on a process flow

---

## Documentation types

### 1. System Architecture Document (SAD)

Use this when accompanying High-Level or Low-Level Architecture diagrams.

**Structure:**

1. **Executive Summary**: High-level purpose of the system.
2. **Architecture Overview**: Explanation of the chosen pattern (Monolith, Microservices, etc.).
3. **Diagram Reference**: Link to the `.drawio` file.
4. **Key Components**: Detailed description of each box in the diagram.
5. **Technology Stack**: Languages, frameworks, and tools used.
6. **Data Flow**: How data moves through the system.
7. **Infrastructure**: Hosting, scaling, and security considerations.

### 2. API / Sequence Documentation

Use this when accompanying Sequence Diagrams.

**Structure:**

1. **Flow Name**: Name of the interaction (e.g., "User Login Flow").
2. **Actors**: Who is involved (User, Client, Server, DB).
3. **Pre-conditions**: What must be true before this flow starts.
4. **Step-by-Step Walkthrough**: Detailed explanation of each arrow in the sequence.
5. **Data Payloads**: Important data being exchanged (optional).
6. **Error Handling**: What happens if something goes wrong.

### 3. Database Schema Documentation

Use this when accompanying Entity-Relationship Diagrams (ERD).

**Structure:**

1. **Domain Overview**: What part of the business this model supports.
2. **Entities**: List of tables with descriptions.
    - **Attributes**: Key columns and their constraints.
3. **Relationships**: Explanation of how entities interact (e.g., "One User has Many Orders").
4. **Normalization Strategy**: Why tables are structured this way.

### 4. Process Guide / SOP

Use this when accompanying Process Flows or Swimlanes.

**Structure:**

1. **Objective**: What this process achieves.
2. **Roles**: Who is responsible (mapped to swimlanes).
3. **Trigger**: What starts the process.
4. **Procedure**: clearly numbered steps corresponding to diagram nodes.
5. **Decision Points**: Logic for branches (If X, then Y).
6. **Outcome**: The final result.

---

## Process

1. **Analyze the Request**: Determine which type of documentation is needed.
2. **Reference the Diagram**: If a diagram exists or is being created, ensure the docs match the visual elements 1:1.
3. **Identify Key Information**:
    - **WHO** (Components/Actors)
    - **HOW** (Relationships/Flows)
    - **WHY** (Rationale/Decisions)
4. **Generate Markdown**: Create a `.md` file.

---

## Output Format

Save as: `[topic]-documentation.md`

**Example Template:**

```markdown
# [System Name] Architecture

## Overview
[Brief description]

## Diagram
![Architecture Diagram]([topic]-architecture.drawio)

## Components
- **Frontend**: [Description]
- **API Gateway**: [Description]
...

## Design Decisions
- Chosen **Redis** for caching because...
```

---

## Writing Tips

- **Be Clear**: Use simple, direct language.
- **Match the Diagram**: Use the exact same names for components as in the diagram.
- **Explain "Why"**: Don't just list components; explain why they are there and how they interact.
- **Use Lists**: Bullet points are easier to read than wall-of-text paragraphs.
