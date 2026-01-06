# Draw.io XML Format Reference

This reference contains everything needed to generate valid `.drawio` files.

---

## Document Structure

Every `.drawio` file is an XML document with this structure:

```xml
<mxfile host="app.diagrams.net" modified="2024-01-01T00:00:00.000Z" agent="Claude" version="22.0.0" type="device">
  <diagram name="Page-1" id="diagram-id">
    <mxGraphModel dx="1422" dy="794" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="850" pageHeight="1100" math="0" shadow="0">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        <!-- Your elements go here -->
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

**CRITICAL:**

- Always include cells with id="0" and id="1" as the root containers
- All other elements must have `parent="1"` or parent set to a container element
- Each element needs a unique ID

---

## Basic Shapes

### Rectangle

```xml
<mxCell id="rect-1" value="My Label" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#dae8fc;strokeColor=#6c8ebf;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="120" height="60" as="geometry"/>
</mxCell>
```

### Rounded Rectangle

```xml
<mxCell id="rect-2" value="Rounded Box" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#d5e8d4;strokeColor=#82b366;arcSize=10;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="120" height="60" as="geometry"/>
</mxCell>
```

### Ellipse/Circle

```xml
<mxCell id="ellipse-1" value="Circle" style="ellipse;whiteSpace=wrap;html=1;fillColor=#fff2cc;strokeColor=#d6b656;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="80" height="80" as="geometry"/>
</mxCell>
```

### Diamond (Decision)

```xml
<mxCell id="diamond-1" value="Decision?" style="rhombus;whiteSpace=wrap;html=1;fillColor=#ffe6cc;strokeColor=#d79b00;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="100" height="80" as="geometry"/>
</mxCell>
```

### Cylinder (Database)

```xml
<mxCell id="db-1" value="Database" style="shape=cylinder3;whiteSpace=wrap;html=1;boundedLbl=1;backgroundOutline=1;size=15;fillColor=#e1d5e7;strokeColor=#9673a6;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="80" height="100" as="geometry"/>
</mxCell>
```

### Cloud

```xml
<mxCell id="cloud-1" value="Cloud Service" style="ellipse;shape=cloud;whiteSpace=wrap;html=1;fillColor=#dae8fc;strokeColor=#6c8ebf;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="140" height="80" as="geometry"/>
</mxCell>
```

### Actor (Stick Figure)

```xml
<mxCell id="actor-1" value="User" style="shape=umlActor;verticalLabelPosition=bottom;verticalAlign=top;html=1;outlineConnect=0;fillColor=#f8cecc;strokeColor=#b85450;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="30" height="60" as="geometry"/>
</mxCell>
```

---

## Connectors/Arrows

### Basic Arrow

```xml
<mxCell id="arrow-1" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;" edge="1" parent="1" source="rect-1" target="rect-2">
  <mxGeometry relative="1" as="geometry"/>
</mxCell>
```

### Arrow with Label

```xml
<mxCell id="arrow-2" value="sends" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;labelBackgroundColor=#ffffff;" edge="1" parent="1" source="rect-1" target="rect-2">
  <mxGeometry relative="1" as="geometry"/>
</mxCell>
```

### Dashed Arrow

```xml
<mxCell id="arrow-3" value="optional" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;dashed=1;dashPattern=8 8;" edge="1" parent="1" source="rect-1" target="rect-2">
  <mxGeometry relative="1" as="geometry"/>
</mxCell>
```

### Curved Arrow

```xml
<mxCell id="arrow-4" value="" style="edgeStyle=elbowEdgeStyle;rounded=1;orthogonalLoop=1;jettySize=auto;html=1;curved=1;strokeWidth=2;" edge="1" parent="1" source="rect-1" target="rect-2">
  <mxGeometry relative="1" as="geometry"/>
</mxCell>
```

### Bidirectional Arrow

```xml
<mxCell id="arrow-5" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;startArrow=classic;endArrow=classic;" edge="1" parent="1" source="rect-1" target="rect-2">
  <mxGeometry relative="1" as="geometry"/>
</mxCell>
```

---

## Edge Styles

| Style | Description | Use Case |
|-------|-------------|----------|
| `orthogonalEdgeStyle` | 90-degree angles | Process flows, architecture |
| `elbowEdgeStyle` | Elbow connectors | Compact diagrams |
| `entityRelationEdgeStyle` | ER diagram style | Database relationships |
| `segmentEdgeStyle` | Straight segments | Sequence diagrams |
| `curved=1` | Curved lines | Mind maps, organic flows |

---

## Arrow Types

| Property | Value | Description |
|----------|-------|-------------|
| `endArrow` | `classic` | Standard arrow |
| `endArrow` | `block` | Filled triangle |
| `endArrow` | `open` | Open arrow |
| `endArrow` | `none` | No arrow |
| `startArrow` | `classic` | Arrow at start |
| `startArrow` | `diamond` | Diamond (composition) |
| `startArrow` | `diamondThin` | Hollow diamond (aggregation) |

---

## Entity-Relationship Diagram Elements

### Entity Table

```xml
<mxCell id="entity-1" value="User" style="swimlane;fontStyle=1;childLayout=stackLayout;horizontal=1;startSize=30;horizontalStack=0;resizeParent=1;resizeParentMax=0;resizeLast=0;collapsible=1;marginBottom=0;whiteSpace=wrap;html=1;fillColor=#dae8fc;strokeColor=#6c8ebf;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="140" height="120" as="geometry"/>
</mxCell>
<mxCell id="entity-1-attr1" value="id: INT (PK)" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;spacingLeft=4;spacingRight=4;overflow=hidden;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;rotatable=0;whiteSpace=wrap;html=1;fontStyle=1" vertex="1" parent="entity-1">
  <mxGeometry y="30" width="140" height="30" as="geometry"/>
</mxCell>
<mxCell id="entity-1-attr2" value="username: VARCHAR" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;spacingLeft=4;spacingRight=4;overflow=hidden;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;rotatable=0;whiteSpace=wrap;html=1;" vertex="1" parent="entity-1">
  <mxGeometry y="60" width="140" height="30" as="geometry"/>
</mxCell>
<mxCell id="entity-1-attr3" value="email: VARCHAR" style="text;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;spacingLeft=4;spacingRight=4;overflow=hidden;points=[[0,0.5],[1,0.5]];portConstraint=eastwest;rotatable=0;whiteSpace=wrap;html=1;" vertex="1" parent="entity-1">
  <mxGeometry y="90" width="140" height="30" as="geometry"/>
</mxCell>
```

### Relationship Connector

```xml
<!-- One-to-Many -->
<mxCell id="rel-1" value="has many" style="edgeStyle=entityRelationEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;startArrow=none;endArrow=ERmany;strokeWidth=2;" edge="1" parent="1" source="entity-1" target="entity-2">
  <mxGeometry relative="1" as="geometry"/>
</mxCell>

<!-- One-to-One -->
<mxCell id="rel-2" value="has one" style="edgeStyle=entityRelationEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;startArrow=ERone;endArrow=ERone;strokeWidth=2;" edge="1" parent="1" source="entity-1" target="entity-3">
  <mxGeometry relative="1" as="geometry"/>
</mxCell>

<!-- Many-to-Many -->
<mxCell id="rel-3" value="belongs to" style="edgeStyle=entityRelationEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;startArrow=ERmany;endArrow=ERmany;strokeWidth=2;" edge="1" parent="1" source="entity-2" target="entity-3">
  <mxGeometry relative="1" as="geometry"/>
</mxCell>
```

---

## Sequence Diagram Elements

### Lifeline (Actor/Object)

```xml
<mxCell id="lifeline-1" value="User" style="shape=umlLifeline;perimeter=lifelinePerimeter;whiteSpace=wrap;html=1;container=1;dropTarget=0;collapsible=0;recursiveResize=0;outlineConnect=0;portConstraint=eastwest;newEdgeStyle={&quot;edgeStyle&quot;:&quot;elbowEdgeStyle&quot;,&quot;elbow&quot;:&quot;vertical&quot;,&quot;curved&quot;:0,&quot;rounded&quot;:0};fillColor=#dae8fc;strokeColor=#6c8ebf;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="100" height="400" as="geometry"/>
</mxCell>
```

### Activation Box

```xml
<mxCell id="activation-1" value="" style="html=1;points=[];perimeter=orthogonalPerimeter;outlineConnect=0;targetShapes=umlLifeline;portConstraint=eastwest;newEdgeStyle={&quot;edgeStyle&quot;:&quot;elbowEdgeStyle&quot;,&quot;elbow&quot;:&quot;vertical&quot;,&quot;curved&quot;:0,&quot;rounded&quot;:0};fillColor=#f8cecc;strokeColor=#b85450;" vertex="1" parent="lifeline-1">
  <mxGeometry x="45" y="80" width="10" height="60" as="geometry"/>
</mxCell>
```

### Message Arrow

```xml
<mxCell id="msg-1" value="login(credentials)" style="html=1;verticalAlign=bottom;endArrow=block;edgeStyle=elbowEdgeStyle;elbow=vertical;curved=0;rounded=0;strokeWidth=2;" edge="1" parent="1" source="lifeline-1" target="lifeline-2">
  <mxGeometry relative="1" as="geometry">
    <mxPoint x="150" y="200" as="sourcePoint"/>
    <mxPoint x="250" y="200" as="targetPoint"/>
  </mxGeometry>
</mxCell>
```

### Return Message (Dashed)

```xml
<mxCell id="return-1" value="token" style="html=1;verticalAlign=bottom;endArrow=open;dashed=1;endSize=8;edgeStyle=elbowEdgeStyle;elbow=vertical;curved=0;rounded=0;strokeWidth=2;" edge="1" parent="1" source="lifeline-2" target="lifeline-1">
  <mxGeometry relative="1" as="geometry">
    <mxPoint x="250" y="240" as="sourcePoint"/>
    <mxPoint x="150" y="240" as="targetPoint"/>
  </mxGeometry>
</mxCell>
```

---

## Architecture Diagram Elements

### Component Box

```xml
<mxCell id="component-1" value="&lt;b&gt;API Gateway&lt;/b&gt;&lt;br&gt;&lt;i&gt;&amp;lt;&amp;lt;component&amp;gt;&amp;gt;&lt;/i&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#d5e8d4;strokeColor=#82b366;strokeWidth=2;arcSize=10;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="140" height="80" as="geometry"/>
</mxCell>
```

### Container (System Boundary)

```xml
<mxCell id="container-1" value="Microservices Layer" style="swimlane;whiteSpace=wrap;html=1;fillColor=#f5f5f5;strokeColor=#666666;fontStyle=1;fontSize=14;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="400" height="300" as="geometry"/>
</mxCell>
```

### Server/Node

```xml
<mxCell id="server-1" value="&lt;b&gt;Web Server&lt;/b&gt;&lt;br&gt;nginx" style="shape=cube;whiteSpace=wrap;html=1;boundedLbl=1;backgroundOutline=1;darkOpacity=0.05;darkOpacity2=0.1;fillColor=#dae8fc;strokeColor=#6c8ebf;size=10;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="100" height="80" as="geometry"/>
</mxCell>
```

### Database Icon

```xml
<mxCell id="db-icon-1" value="&lt;b&gt;PostgreSQL&lt;/b&gt;" style="shape=cylinder3;whiteSpace=wrap;html=1;boundedLbl=1;backgroundOutline=1;size=15;fillColor=#e1d5e7;strokeColor=#9673a6;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="80" height="100" as="geometry"/>
</mxCell>
```

---

## Style Properties

### Common Style Attributes

| Property | Values | Description |
|----------|--------|-------------|
| `fillColor` | `#rrggbb` | Background color |
| `strokeColor` | `#rrggbb` | Border color |
| `strokeWidth` | `1`, `2`, `3` | Border thickness |
| `rounded` | `0`, `1` | Rounded corners |
| `dashed` | `1` | Dashed border |
| `dashPattern` | `8 8` | Dash pattern |
| `fontSize` | `12`, `14`, `16` | Text size |
| `fontStyle` | `0` (normal), `1` (bold), `2` (italic), `3` (bold+italic) | Text style |
| `fontColor` | `#rrggbb` | Text color |
| `align` | `left`, `center`, `right` | Horizontal alignment |
| `verticalAlign` | `top`, `middle`, `bottom` | Vertical alignment |

### Edge Style Properties

| Property | Values | Description |
|----------|--------|-------------|
| `edgeStyle` | `orthogonalEdgeStyle`, `elbowEdgeStyle`, `entityRelationEdgeStyle` | Routing style |
| `curved` | `0`, `1` | Curved or straight |
| `rounded` | `0`, `1` | Rounded corners |
| `jettySize` | `auto`, number | Connector offset |
| `orthogonalLoop` | `1` | Enable orthogonal routing |

---

## Text Formatting

### HTML in Labels

Draw.io supports HTML in cell values:

```xml
<mxCell id="text-1" value="&lt;b&gt;Bold Text&lt;/b&gt;&lt;br&gt;&lt;i&gt;Italic&lt;/i&gt;&lt;br&gt;&lt;u&gt;Underline&lt;/u&gt;" style="text;html=1;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;whiteSpace=wrap;rounded=0;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="120" height="60" as="geometry"/>
</mxCell>
```

### Multi-line Text

Use `&lt;br&gt;` for line breaks:

```xml
value="Line 1&lt;br&gt;Line 2&lt;br&gt;Line 3"
```

---

## Positioning and Layout

### Absolute Positioning

```xml
<mxGeometry x="100" y="100" width="120" height="60" as="geometry"/>
```

- `x`, `y`: Top-left corner position
- `width`, `height`: Element dimensions

### Relative Positioning (for children)

```xml
<mxGeometry y="30" width="140" height="30" as="geometry"/>
```

Used for elements inside containers (like table rows).

---

## Swimlane Layouts

### Horizontal Swimlane

```xml
<mxCell id="pool-1" value="Process Name" style="swimlane;html=1;childLayout=stackLayout;resizeParent=1;resizeParentMax=0;horizontal=1;startSize=20;horizontalStack=0;fillColor=#f5f5f5;strokeColor=#666666;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="600" height="400" as="geometry"/>
</mxCell>
<mxCell id="lane-1" value="Customer" style="swimlane;html=1;startSize=20;horizontal=0;fillColor=#dae8fc;strokeColor=#6c8ebf;" vertex="1" parent="pool-1">
  <mxGeometry y="20" width="600" height="120" as="geometry"/>
</mxCell>
<mxCell id="lane-2" value="Sales" style="swimlane;html=1;startSize=20;horizontal=0;fillColor=#d5e8d4;strokeColor=#82b366;" vertex="1" parent="pool-1">
  <mxGeometry y="140" width="600" height="120" as="geometry"/>
</mxCell>
```

---

## Color Schemes

### Professional Palette

| Category | Fill Color | Stroke Color |
|----------|-----------|--------------|
| Primary | `#dae8fc` | `#6c8ebf` |
| Success | `#d5e8d4` | `#82b366` |
| Warning | `#fff2cc` | `#d6b656` |
| Error | `#f8cecc` | `#b85450` |
| Info | `#e1d5e7` | `#9673a6` |
| Neutral | `#f5f5f5` | `#666666` |

### Architecture Colors

| Component | Fill Color | Stroke Color |
|-----------|-----------|--------------|
| Frontend | `#dae8fc` | `#6c8ebf` |
| Backend | `#d5e8d4` | `#82b366` |
| Database | `#e1d5e7` | `#9673a6` |
| External | `#fff2cc` | `#d6b656` |
| Queue/Cache | `#ffe6cc` | `#d79b00` |

---

## Best Practices

### 1. Consistent Spacing

- Horizontal gap between shapes: **100-150px**
- Vertical gap between shapes: **80-120px**
- Swimlane height: **120-150px**

### 2. Proper Connectors

- Always use `source` and `target` attributes
- Set `edge="1"` for all connectors
- Use `edgeStyle=orthogonalEdgeStyle` for clean routing

### 3. Layering

- Background elements first
- Containers before contents
- Connectors last

### 4. IDs

- Use descriptive IDs: `user-entity`, `login-msg`, `api-gateway`
- Ensure all IDs are unique
- Reference IDs correctly in source/target

---

## Validation Checklist

Before outputting the `.drawio` file:

**Structure:**

- [ ] Root cells (id="0" and id="1") are present
- [ ] All elements have unique IDs
- [ ] All elements have `parent` attribute
- [ ] mxGeometry is properly defined for all elements

**Connectors:**

- [ ] All arrows have `source` and `target` attributes
- [ ] `edge="1"` is set for all connectors
- [ ] `edgeStyle` is specified
- [ ] Labels use `labelBackgroundColor` for readability

**Styling:**

- [ ] Colors follow a consistent scheme
- [ ] Text is readable (good contrast)
- [ ] HTML entities are properly escaped (`&lt;`, `&gt;`, `&amp;`)

**Layout:**

- [ ] Elements don't overlap
- [ ] Spacing is consistent
- [ ] Alignment is clean

---

## Complete Example

```xml
<mxfile host="app.diagrams.net">
  <diagram name="Page-1" id="diagram-1">
    <mxGraphModel dx="1422" dy="794" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="850" pageHeight="1100">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        
        <!-- Rectangle -->
        <mxCell id="rect-1" value="Start" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#d5e8d4;strokeColor=#82b366;" vertex="1" parent="1">
          <mxGeometry x="100" y="100" width="120" height="60" as="geometry"/>
        </mxCell>
        
        <!-- Rectangle 2 -->
        <mxCell id="rect-2" value="Process" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#dae8fc;strokeColor=#6c8ebf;" vertex="1" parent="1">
          <mxGeometry x="300" y="100" width="120" height="60" as="geometry"/>
        </mxCell>
        
        <!-- Arrow -->
        <mxCell id="arrow-1" value="" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;" edge="1" parent="1" source="rect-1" target="rect-2">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

---

*This reference covers the essential Draw.io XML format. For specific diagram types, refer to the workflow files.*
