# Deployment Diagram Workflow

Create infrastructure and deployment diagrams showing **Kubernetes clusters**, **CI/CD pipelines**, **cloud infrastructure**, and **container orchestration** with proper icons.

---

## Mandatory Deliverables

**You MUST generate TWO files:**

1. **`[system-name]-deployment.drawio`** - Infrastructure diagram with proper icons
2. **`[system-name]-deployment-docs.md`** - Deployment documentation

**DO NOT generate just one file. Both are required.**

---

## When to Use

- Kubernetes cluster architecture
- CI/CD pipeline visualization
- Cloud infrastructure (AWS/Azure/GCP)
- Container deployment strategy
- DevOps documentation
- Infrastructure as Code documentation

---

## Deployment Types

### 1. Kubernetes Deployment

**Components to show:**

- Cluster (master nodes)
- Namespaces
- Deployments/StatefulSets
- Services (ClusterIP, LoadBalancer)
- Ingress Controller
- ConfigMaps/Secrets
- Persistent Volumes

### 2. AWS Infrastructure

**Components to show:**

- VPC with subnets
- EC2/ECS/EKS
- RDS/DynamoDB
- S3/CloudFront
- ALB/NLB
- Route 53
- Security Groups

### 3. CI/CD Pipeline

**Components to show:**

- Source Control (GitHub/GitLab)
- Build Stage (compile, test)
- Container Registry
- Deployment Stage
- Environment progression (Dev→Staging→Prod)

---

## Process

### Step 1: Gather Requirements

Ask for:

- What cloud provider? (AWS, Azure, GCP, on-prem)
- Kubernetes or traditional VMs?
- CI/CD tooling (GitHub Actions, Jenkins, ArgoCD)
- Number of environments
- Key infrastructure components

### Step 2: Map Components to Icons

| Component | Icon/Shape |
|-----------|-----------|
| Kubernetes Pod | K8s Pod icon (blue hexagon) |
| Kubernetes Service | K8s Service icon |
| AWS EC2 | AWS compute icon |
| AWS RDS | AWS database icon |
| Docker Container | Docker whale icon |
| GitHub | GitHub logo box |
| ArgoCD | ArgoCD box |

### Step 3: Generate BOTH Outputs

**Output 1: Diagram (`[name]-deployment.drawio`)**
**Output 2: Documentation (`[name]-deployment-docs.md`)**

---

## Layout Rules

### Kubernetes Cluster Layout

```
┌─────────────────────────────────────────────────────────────────┐
│  Kubernetes Cluster                                              │
│  ┌───────────────────────────────────────────────────────────┐  │
│  │  namespace: production                                      │  │
│  │                                                             │  │
│  │  ┌─────────┐   ┌─────────┐   ┌─────────┐                   │  │
│  │  │ Ingress │ → │ Service │ → │ Deployment │ → [Pod] [Pod]  │  │
│  │  └─────────┘   └─────────┘   └──────────┘                   │  │
│  │                                                             │  │
│  │  ConfigMap    Secret    PVC                                 │  │
│  └───────────────────────────────────────────────────────────┘  │
└─────────────────────────────────────────────────────────────────┘
```

### CI/CD Pipeline Layout

```
[GitHub] → [Build] → [Test] → [Container Registry] → [Deploy to K8s]
                                                            ↓
                                                     [Dev] → [Staging] → [Prod]
```

---

## Complete Kubernetes Diagram Example

```xml
<mxfile host="app.diagrams.net" modified="2024-01-01T00:00:00.000Z" agent="Claude" version="22.0.0">
  <diagram name="Kubernetes Deployment" id="k8s-deployment">
    <mxGraphModel dx="1422" dy="794" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1600" pageHeight="1200">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        
        <!-- ============ KUBERNETES CLUSTER ============ -->
        
        <!-- Cluster Container -->
        <mxCell id="k8s-cluster" value="&lt;b&gt;Kubernetes Cluster (EKS)&lt;/b&gt;" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#e8f0fe;strokeColor=#326CE5;strokeWidth=3;verticalAlign=top;align=left;spacingLeft=15;fontSize=14;fontColor=#1a1a1a;fontStyle=1;" vertex="1" parent="1">
          <mxGeometry x="100" y="100" width="1200" height="800" as="geometry"/>
        </mxCell>
        
        <!-- ============ INGRESS ============ -->
        
        <!-- Ingress Controller -->
        <mxCell id="ingress" value="&lt;b&gt;Ingress&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;nginx-ingress&lt;/font&gt;" style="sketch=0;html=1;dashed=0;whitespace=wrap;fillColor=#326CE5;strokeColor=#ffffff;points=[[0.005,0.63,0],[0.1,0.2,0],[0.9,0.2,0],[0.995,0.63,0],[0.72,0.99,0],[0.5,1,0],[0.28,0.99,0]];verticalLabelPosition=bottom;align=center;verticalAlign=top;shape=mxgraph.kubernetes.icon;prIcon=ing;fontSize=12;fontColor=#1a1a1a;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="180" y="300" width="70" height="67" as="geometry"/>
        </mxCell>
        
        <!-- ============ NAMESPACES ============ -->
        
        <!-- Production Namespace -->
        <mxCell id="ns-production" value="namespace: production" style="rounded=0;whiteSpace=wrap;html=1;fillColor=none;strokeColor=#326CE5;strokeWidth=2;dashed=1;dashPattern=8 8;verticalAlign=top;align=left;spacingLeft=10;fontSize=12;fontColor=#326CE5;" vertex="1" parent="1">
          <mxGeometry x="300" y="180" width="450" height="350" as="geometry"/>
        </mxCell>
        
        <!-- ============ API SERVICE ============ -->
        
        <!-- API Deployment -->
        <mxCell id="deploy-api" value="&lt;b&gt;api-deployment&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;replicas: 3&lt;/font&gt;" style="sketch=0;html=1;dashed=0;whitespace=wrap;fillColor=#326CE5;strokeColor=#ffffff;points=[[0.005,0.63,0],[0.1,0.2,0],[0.9,0.2,0],[0.995,0.63,0],[0.72,0.99,0],[0.5,1,0],[0.28,0.99,0]];verticalLabelPosition=bottom;align=center;verticalAlign=top;shape=mxgraph.kubernetes.icon;prIcon=deploy;fontSize=11;fontColor=#1a1a1a;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="450" y="220" width="60" height="57" as="geometry"/>
        </mxCell>
        
        <!-- API Service -->
        <mxCell id="svc-api" value="&lt;b&gt;api-svc&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;ClusterIP&lt;/font&gt;" style="sketch=0;html=1;dashed=0;whitespace=wrap;fillColor=#326CE5;strokeColor=#ffffff;points=[[0.005,0.63,0],[0.1,0.2,0],[0.9,0.2,0],[0.995,0.63,0],[0.72,0.99,0],[0.5,1,0],[0.28,0.99,0]];verticalLabelPosition=bottom;align=center;verticalAlign=top;shape=mxgraph.kubernetes.icon;prIcon=svc;fontSize=11;fontColor=#1a1a1a;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="330" y="300" width="60" height="57" as="geometry"/>
        </mxCell>
        
        <!-- API Pods -->
        <mxCell id="pod-api-1" value="&lt;font size='2'&gt;pod-1&lt;/font&gt;" style="sketch=0;html=1;dashed=0;whitespace=wrap;fillColor=#326CE5;strokeColor=#ffffff;points=[[0.005,0.63,0],[0.1,0.2,0],[0.9,0.2,0],[0.995,0.63,0],[0.72,0.99,0],[0.5,1,0],[0.28,0.99,0]];verticalLabelPosition=bottom;align=center;verticalAlign=top;shape=mxgraph.kubernetes.icon;prIcon=pod;fontSize=10;fontColor=#1a1a1a;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="540" y="210" width="50" height="47" as="geometry"/>
        </mxCell>
        
        <mxCell id="pod-api-2" value="&lt;font size='2'&gt;pod-2&lt;/font&gt;" style="sketch=0;html=1;dashed=0;whitespace=wrap;fillColor=#326CE5;strokeColor=#ffffff;points=[[0.005,0.63,0],[0.1,0.2,0],[0.9,0.2,0],[0.995,0.63,0],[0.72,0.99,0],[0.5,1,0],[0.28,0.99,0]];verticalLabelPosition=bottom;align=center;verticalAlign=top;shape=mxgraph.kubernetes.icon;prIcon=pod;fontSize=10;fontColor=#1a1a1a;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="600" y="210" width="50" height="47" as="geometry"/>
        </mxCell>
        
        <mxCell id="pod-api-3" value="&lt;font size='2'&gt;pod-3&lt;/font&gt;" style="sketch=0;html=1;dashed=0;whitespace=wrap;fillColor=#326CE5;strokeColor=#ffffff;points=[[0.005,0.63,0],[0.1,0.2,0],[0.9,0.2,0],[0.995,0.63,0],[0.72,0.99,0],[0.5,1,0],[0.28,0.99,0]];verticalLabelPosition=bottom;align=center;verticalAlign=top;shape=mxgraph.kubernetes.icon;prIcon=pod;fontSize=10;fontColor=#1a1a1a;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="660" y="210" width="50" height="47" as="geometry"/>
        </mxCell>
        
        <!-- ============ WORKER SERVICE ============ -->
        
        <!-- Worker Deployment -->
        <mxCell id="deploy-worker" value="&lt;b&gt;worker-deployment&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;replicas: 2&lt;/font&gt;" style="sketch=0;html=1;dashed=0;whitespace=wrap;fillColor=#326CE5;strokeColor=#ffffff;points=[[0.005,0.63,0],[0.1,0.2,0],[0.9,0.2,0],[0.995,0.63,0],[0.72,0.99,0],[0.5,1,0],[0.28,0.99,0]];verticalLabelPosition=bottom;align=center;verticalAlign=top;shape=mxgraph.kubernetes.icon;prIcon=deploy;fontSize=11;fontColor=#1a1a1a;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="450" y="380" width="60" height="57" as="geometry"/>
        </mxCell>
        
        <!-- Worker Pods -->
        <mxCell id="pod-worker-1" value="&lt;font size='2'&gt;pod-1&lt;/font&gt;" style="sketch=0;html=1;dashed=0;whitespace=wrap;fillColor=#326CE5;strokeColor=#ffffff;points=[[0.005,0.63,0],[0.1,0.2,0],[0.9,0.2,0],[0.995,0.63,0],[0.72,0.99,0],[0.5,1,0],[0.28,0.99,0]];verticalLabelPosition=bottom;align=center;verticalAlign=top;shape=mxgraph.kubernetes.icon;prIcon=pod;fontSize=10;fontColor=#1a1a1a;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="540" y="380" width="50" height="47" as="geometry"/>
        </mxCell>
        
        <mxCell id="pod-worker-2" value="&lt;font size='2'&gt;pod-2&lt;/font&gt;" style="sketch=0;html=1;dashed=0;whitespace=wrap;fillColor=#326CE5;strokeColor=#ffffff;points=[[0.005,0.63,0],[0.1,0.2,0],[0.9,0.2,0],[0.995,0.63,0],[0.72,0.99,0],[0.5,1,0],[0.28,0.99,0]];verticalLabelPosition=bottom;align=center;verticalAlign=top;shape=mxgraph.kubernetes.icon;prIcon=pod;fontSize=10;fontColor=#1a1a1a;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="600" y="380" width="50" height="47" as="geometry"/>
        </mxCell>
        
        <!-- ============ DATABASE NAMESPACE ============ -->
        
        <!-- Database Namespace -->
        <mxCell id="ns-database" value="namespace: database" style="rounded=0;whiteSpace=wrap;html=1;fillColor=none;strokeColor=#9673a6;strokeWidth=2;dashed=1;dashPattern=8 8;verticalAlign=top;align=left;spacingLeft=10;fontSize=12;fontColor=#9673a6;" vertex="1" parent="1">
          <mxGeometry x="800" y="180" width="450" height="350" as="geometry"/>
        </mxCell>
        
        <!-- PostgreSQL StatefulSet -->
        <mxCell id="sts-postgres" value="&lt;b&gt;postgres-sts&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;StatefulSet&lt;/font&gt;" style="sketch=0;html=1;dashed=0;whitespace=wrap;fillColor=#326CE5;strokeColor=#ffffff;points=[[0.005,0.63,0],[0.1,0.2,0],[0.9,0.2,0],[0.995,0.63,0],[0.72,0.99,0],[0.5,1,0],[0.28,0.99,0]];verticalLabelPosition=bottom;align=center;verticalAlign=top;shape=mxgraph.kubernetes.icon;prIcon=sts;fontSize=11;fontColor=#1a1a1a;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="870" y="230" width="60" height="57" as="geometry"/>
        </mxCell>
        
        <!-- PostgreSQL Service -->
        <mxCell id="svc-postgres" value="&lt;b&gt;postgres-svc&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;ClusterIP&lt;/font&gt;" style="sketch=0;html=1;dashed=0;whitespace=wrap;fillColor=#326CE5;strokeColor=#ffffff;points=[[0.005,0.63,0],[0.1,0.2,0],[0.9,0.2,0],[0.995,0.63,0],[0.72,0.99,0],[0.5,1,0],[0.28,0.99,0]];verticalLabelPosition=bottom;align=center;verticalAlign=top;shape=mxgraph.kubernetes.icon;prIcon=svc;fontSize=11;fontColor=#1a1a1a;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="970" y="230" width="60" height="57" as="geometry"/>
        </mxCell>
        
        <!-- PostgreSQL PVC -->
        <mxCell id="pvc-postgres" value="&lt;b&gt;postgres-pvc&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;100Gi&lt;/font&gt;" style="sketch=0;html=1;dashed=0;whitespace=wrap;fillColor=#326CE5;strokeColor=#ffffff;points=[[0.005,0.63,0],[0.1,0.2,0],[0.9,0.2,0],[0.995,0.63,0],[0.72,0.99,0],[0.5,1,0],[0.28,0.99,0]];verticalLabelPosition=bottom;align=center;verticalAlign=top;shape=mxgraph.kubernetes.icon;prIcon=pvc;fontSize=11;fontColor=#1a1a1a;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="1070" y="230" width="60" height="57" as="geometry"/>
        </mxCell>
        
        <!-- Redis Deployment -->
        <mxCell id="deploy-redis" value="&lt;b&gt;redis-deploy&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;replicas: 3&lt;/font&gt;" style="sketch=0;html=1;dashed=0;whitespace=wrap;fillColor=#326CE5;strokeColor=#ffffff;points=[[0.005,0.63,0],[0.1,0.2,0],[0.9,0.2,0],[0.995,0.63,0],[0.72,0.99,0],[0.5,1,0],[0.28,0.99,0]];verticalLabelPosition=bottom;align=center;verticalAlign=top;shape=mxgraph.kubernetes.icon;prIcon=deploy;fontSize=11;fontColor=#1a1a1a;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="870" y="380" width="60" height="57" as="geometry"/>
        </mxCell>
        
        <!-- Redis Service -->
        <mxCell id="svc-redis" value="&lt;b&gt;redis-svc&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;ClusterIP&lt;/font&gt;" style="sketch=0;html=1;dashed=0;whitespace=wrap;fillColor=#326CE5;strokeColor=#ffffff;points=[[0.005,0.63,0],[0.1,0.2,0],[0.9,0.2,0],[0.995,0.63,0],[0.72,0.99,0],[0.5,1,0],[0.28,0.99,0]];verticalLabelPosition=bottom;align=center;verticalAlign=top;shape=mxgraph.kubernetes.icon;prIcon=svc;fontSize=11;fontColor=#1a1a1a;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="970" y="380" width="60" height="57" as="geometry"/>
        </mxCell>
        
        <!-- ============ CONFIG ============ -->
        
        <!-- ConfigMap -->
        <mxCell id="configmap" value="&lt;b&gt;app-config&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;ConfigMap&lt;/font&gt;" style="sketch=0;html=1;dashed=0;whitespace=wrap;fillColor=#326CE5;strokeColor=#ffffff;points=[[0.005,0.63,0],[0.1,0.2,0],[0.9,0.2,0],[0.995,0.63,0],[0.72,0.99,0],[0.5,1,0],[0.28,0.99,0]];verticalLabelPosition=bottom;align=center;verticalAlign=top;shape=mxgraph.kubernetes.icon;prIcon=cm;fontSize=11;fontColor=#1a1a1a;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="320" y="600" width="60" height="57" as="geometry"/>
        </mxCell>
        
        <!-- Secret -->
        <mxCell id="secret" value="&lt;b&gt;app-secrets&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;Secret&lt;/font&gt;" style="sketch=0;html=1;dashed=0;whitespace=wrap;fillColor=#326CE5;strokeColor=#ffffff;points=[[0.005,0.63,0],[0.1,0.2,0],[0.9,0.2,0],[0.995,0.63,0],[0.72,0.99,0],[0.5,1,0],[0.28,0.99,0]];verticalLabelPosition=bottom;align=center;verticalAlign=top;shape=mxgraph.kubernetes.icon;prIcon=secret;fontSize=11;fontColor=#1a1a1a;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="420" y="600" width="60" height="57" as="geometry"/>
        </mxCell>
        
        <!-- ============ EXTERNAL RESOURCES ============ -->
        
        <!-- AWS EKS Label -->
        <mxCell id="aws-eks-label" value="&lt;b&gt;AWS EKS&lt;/b&gt;&lt;br&gt;us-east-1" style="text;html=1;strokeColor=none;fillColor=none;align=right;verticalAlign=top;fontSize=14;fontColor=#232F3E;" vertex="1" parent="1">
          <mxGeometry x="1150" y="110" width="120" height="40" as="geometry"/>
        </mxCell>
        
        <!-- Load Balancer (external) -->
        <mxCell id="alb" value="&lt;b&gt;ALB&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;AWS Load Balancer&lt;/font&gt;" style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=#F78E04;gradientDirection=north;fillColor=#D05C17;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=11;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.elastic_load_balancing;" vertex="1" parent="1">
          <mxGeometry x="50" y="300" width="60" height="60" as="geometry"/>
        </mxCell>
        
        <!-- ============ CONNECTIONS ============ -->
        
        <!-- ALB to Ingress -->
        <mxCell id="conn-alb-ingress" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#D05C17;" edge="1" parent="1" source="alb" target="ingress">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
        <!-- Ingress to Service -->
        <mxCell id="conn-ingress-svc" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#326CE5;" edge="1" parent="1" source="ingress" target="svc-api">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
        <!-- Service to Deployment -->
        <mxCell id="conn-svc-deploy" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#326CE5;" edge="1" parent="1" source="svc-api" target="deploy-api">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
        <!-- Deployment to Pods -->
        <mxCell id="conn-deploy-pod1" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=1;strokeColor=#326CE5;" edge="1" parent="1" source="deploy-api" target="pod-api-1">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
        <!-- API to Database Services -->
        <mxCell id="conn-api-postgres" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#336791;" edge="1" parent="1" source="deploy-api" target="svc-postgres">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
        <mxCell id="conn-api-redis" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#DC382D;" edge="1" parent="1" source="deploy-api" target="svc-redis">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

---

## CI/CD Pipeline Diagram Example

```xml
<mxfile host="app.diagrams.net">
  <diagram name="CI/CD Pipeline" id="cicd-pipeline">
    <mxGraphModel dx="1422" dy="794" grid="1" gridSize="10" guides="1" tooltips="1" connect="1" arrows="1" fold="1" page="1" pageScale="1" pageWidth="1600" pageHeight="800">
      <root>
        <mxCell id="0"/>
        <mxCell id="1" parent="0"/>
        
        <!-- GitHub -->
        <mxCell id="github" value="&lt;b&gt;GitHub&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;Source Code&lt;/font&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#24292e;strokeColor=#000000;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="80" y="200" width="120" height="60" as="geometry"/>
        </mxCell>
        
        <!-- GitHub Actions -->
        <mxCell id="gh-actions" value="&lt;b&gt;GitHub Actions&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;CI Pipeline&lt;/font&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#2088FF;strokeColor=#1a70d4;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="280" y="200" width="120" height="60" as="geometry"/>
        </mxCell>
        
        <!-- Build Stage -->
        <mxCell id="build-stage" value="&lt;b&gt;Build&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;npm install&lt;br&gt;npm build&lt;/font&gt;" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#f5f5f5;strokeColor=#666666;fontSize=11;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="280" y="320" width="100" height="70" as="geometry"/>
        </mxCell>
        
        <!-- Test Stage -->
        <mxCell id="test-stage" value="&lt;b&gt;Test&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;Unit Tests&lt;br&gt;Integration&lt;/font&gt;" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#f5f5f5;strokeColor=#666666;fontSize=11;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="400" y="320" width="100" height="70" as="geometry"/>
        </mxCell>
        
        <!-- Docker Build -->
        <mxCell id="docker-build" value="&lt;b&gt;Docker Build&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;Build Image&lt;/font&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#0db7ed;strokeColor=#066d9a;fontColor=#ffffff;fontSize=11;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="520" y="320" width="100" height="70" as="geometry"/>
        </mxCell>
        
        <!-- ECR -->
        <mxCell id="ecr" value="&lt;b&gt;ECR&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;Container Registry&lt;/font&gt;" style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=#F78E04;gradientDirection=north;fillColor=#D05C17;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=11;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.ecr;" vertex="1" parent="1">
          <mxGeometry x="680" y="190" width="70" height="70" as="geometry"/>
        </mxCell>
        
        <!-- ArgoCD -->
        <mxCell id="argocd" value="&lt;b&gt;ArgoCD&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;GitOps&lt;/font&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#EF7B4D;strokeColor=#d16a40;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="830" y="200" width="120" height="60" as="geometry"/>
        </mxCell>
        
        <!-- Environments -->
        <mxCell id="env-dev" value="&lt;b&gt;Development&lt;/b&gt;" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#d5e8d4;strokeColor=#82b366;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="1020" y="140" width="120" height="50" as="geometry"/>
        </mxCell>
        
        <mxCell id="env-staging" value="&lt;b&gt;Staging&lt;/b&gt;" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#fff2cc;strokeColor=#d6b656;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="1020" y="210" width="120" height="50" as="geometry"/>
        </mxCell>
        
        <mxCell id="env-prod" value="&lt;b&gt;Production&lt;/b&gt;" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#f8cecc;strokeColor=#b85450;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
          <mxGeometry x="1020" y="280" width="120" height="50" as="geometry"/>
        </mxCell>
        
        <!-- Connections -->
        <mxCell id="conn-1" value="push" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#333333;labelBackgroundColor=#ffffff;fontSize=10;" edge="1" parent="1" source="github" target="gh-actions">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
        <mxCell id="conn-2" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#333333;" edge="1" parent="1" source="build-stage" target="test-stage">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
        <mxCell id="conn-3" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#333333;" edge="1" parent="1" source="test-stage" target="docker-build">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
        <mxCell id="conn-4" value="push" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#0db7ed;labelBackgroundColor=#ffffff;fontSize=10;" edge="1" parent="1" source="docker-build" target="ecr">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
        <mxCell id="conn-5" value="sync" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#EF7B4D;labelBackgroundColor=#ffffff;fontSize=10;" edge="1" parent="1" source="ecr" target="argocd">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
        <mxCell id="conn-6" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#82b366;" edge="1" parent="1" source="argocd" target="env-dev">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
        <mxCell id="conn-7" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#d6b656;" edge="1" parent="1" source="argocd" target="env-staging">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
        <mxCell id="conn-8" style="edgeStyle=orthogonalEdgeStyle;rounded=0;orthogonalLoop=1;jettySize=auto;html=1;strokeWidth=2;strokeColor=#b85450;" edge="1" parent="1" source="argocd" target="env-prod">
          <mxGeometry relative="1" as="geometry"/>
        </mxCell>
        
      </root>
    </mxGraphModel>
  </diagram>
</mxfile>
```

---

## Documentation Template

**Save as: `[system-name]-deployment-docs.md`**

```markdown
# [System Name] Deployment Documentation

**Version:** 1.0  
**Date:** [Date]  
**Author:** [Author]

---

## 1. Overview

### 1.1 Infrastructure
- **Cloud Provider:** AWS
- **Region:** us-east-1
- **Kubernetes:** EKS 1.28

### 1.2 Environments
| Environment | Cluster | Namespace | Purpose |
|------------|---------|-----------|---------|
| Development | eks-dev | dev | Feature testing |
| Staging | eks-staging | staging | Pre-production |
| Production | eks-prod | production | Live traffic |

---

## 2. Kubernetes Resources

### 2.1 Namespaces

| Namespace | Purpose |
|-----------|---------|
| production | Application workloads |
| database | Database StatefulSets |
| monitoring | Prometheus, Grafana |
| ingress-nginx | Ingress controller |

### 2.2 Deployments

| Name | Replicas | Image | Resources |
|------|----------|-------|-----------|
| api-deployment | 3 | app/api:latest | 256Mi/512Mi, 0.25/0.5 CPU |
| worker-deployment | 2 | app/worker:latest | 512Mi/1Gi, 0.5/1 CPU |

### 2.3 StatefulSets

| Name | Replicas | Storage | Purpose |
|------|----------|---------|---------|
| postgres-sts | 1 | 100Gi | Primary database |

### 2.4 Services

| Name | Type | Port | Target |
|------|------|------|--------|
| api-svc | ClusterIP | 3000 | api-deployment |
| postgres-svc | ClusterIP | 5432 | postgres-sts |
| redis-svc | ClusterIP | 6379 | redis-deploy |

### 2.5 Ingress

| Host | Path | Service |
|------|------|---------|
| api.example.com | / | api-svc:3000 |
| ws.example.com | / | websocket-svc:8080 |

---

## 3. CI/CD Pipeline

### 3.1 Pipeline Stages

1. **Source** - GitHub repository trigger on push/PR
2. **Build** - npm install, npm run build
3. **Test** - Unit tests, integration tests, linting
4. **Security Scan** - Snyk vulnerability scanning
5. **Docker Build** - Build container image
6. **Push** - Push to AWS ECR
7. **Deploy** - ArgoCD syncs to Kubernetes

### 3.2 GitHub Actions Workflow

```yaml
name: CI/CD Pipeline
on:
  push:
    branches: [main, develop]
  pull_request:
    branches: [main]

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Setup Node.js
        uses: actions/setup-node@v4
        with:
          node-version: '20'
      - name: Install dependencies
        run: npm ci
      - name: Run tests
        run: npm test
      - name: Build
        run: npm run build
      - name: Build and push Docker image
        uses: docker/build-push-action@v5
        with:
          push: true
          tags: ${{ secrets.ECR_REGISTRY }}/app:${{ github.sha }}
```

### 3.3 ArgoCD Application

```yaml
apiVersion: argoproj.io/v1alpha1
kind: Application
metadata:
  name: app-production
  namespace: argocd
spec:
  project: default
  source:
    repoURL: https://github.com/org/app-manifests
    targetRevision: HEAD
    path: environments/production
  destination:
    server: https://kubernetes.default.svc
    namespace: production
  syncPolicy:
    automated:
      prune: true
      selfHeal: true
```

---

## 4. Configuration

### 4.1 ConfigMaps

| Name | Keys | Purpose |
|------|------|---------|
| app-config | API_URL, LOG_LEVEL, FEATURE_FLAGS | Application settings |

### 4.2 Secrets

| Name | Keys | Source |
|------|------|--------|
| app-secrets | DATABASE_URL, JWT_SECRET, STRIPE_KEY | AWS Secrets Manager |
| docker-registry | .dockerconfigjson | ECR credentials |

---

## 5. Scaling

### 5.1 Horizontal Pod Autoscaler

```yaml
apiVersion: autoscaling/v2
kind: HorizontalPodAutoscaler
metadata:
  name: api-hpa
spec:
  scaleTargetRef:
    apiVersion: apps/v1
    kind: Deployment
    name: api-deployment
  minReplicas: 3
  maxReplicas: 10
  metrics:
    - type: Resource
      resource:
        name: cpu
        target:
          type: Utilization
          averageUtilization: 70
```

### 5.2 Cluster Autoscaler

- **Min nodes:** 3
- **Max nodes:** 10
- **Scale up threshold:** 80% CPU
- **Scale down threshold:** 40% CPU

---

## 6. Monitoring

### 6.1 Prometheus Metrics

- Pod CPU/Memory usage
- Request latency (p50, p95, p99)
- Error rates
- Active connections

### 6.2 Grafana Dashboards

- Kubernetes cluster overview
- Application performance
- Database metrics
- Cost analysis

### 6.3 Alerting Rules

| Alert | Condition | Severity |
|-------|-----------|----------|
| HighErrorRate | error_rate > 5% for 5m | critical |
| HighLatency | p99 > 500ms for 10m | warning |
| PodRestarts | restarts > 3 in 1h | warning |

---

## 7. Disaster Recovery

### 7.1 Backup Strategy

- **Database:** Daily snapshots, 30-day retention
- **Kubernetes:** Velero for cluster backup
- **Secrets:** AWS Secrets Manager with replication

### 7.2 Recovery Procedures

1. Restore database from snapshot
2. Apply Kubernetes manifests from Git
3. Verify all services are healthy
4. Run smoke tests

---

## 8. Runbooks

### 8.1 Deployment Rollback

```bash
# Rollback to previous revision
kubectl rollout undo deployment/api-deployment -n production

# Rollback to specific revision
kubectl rollout undo deployment/api-deployment --to-revision=2 -n production
```

### 8.2 Scale Deployment

```bash
# Manual scale
kubectl scale deployment/api-deployment --replicas=5 -n production
```

### 8.3 View Logs

```bash
# All pods
kubectl logs -l app=api -n production --tail=100

# Specific pod
kubectl logs api-deployment-xxxxx -n production -f
```

---

*Document generated by Architecture Diagrams Skill*

```

---

## Icon Quick Reference

### Kubernetes Icons

| Resource | prIcon Value |
|----------|--------------|
| Pod | `pod` |
| Deployment | `deploy` |
| Service | `svc` |
| StatefulSet | `sts` |
| Ingress | `ing` |
| ConfigMap | `cm` |
| Secret | `secret` |
| PVC | `pvc` |

### AWS Icons

| Service | resIcon Value |
|---------|---------------|
| EC2 | `mxgraph.aws4.ec2` |
| EKS | `mxgraph.aws4.eks` |
| ECR | `mxgraph.aws4.ecr` |
| S3 | `mxgraph.aws4.s3` |
| RDS | `mxgraph.aws4.rds` |
| ALB | `mxgraph.aws4.elastic_load_balancing` |

---

## Output Files

**For a request like "Create Kubernetes deployment diagram":**

1. ✅ `[app-name]-deployment.drawio`
2. ✅ `[app-name]-deployment-docs.md`

**BOTH files are mandatory.**

---

*Deployment Diagrams - Infrastructure and CI/CD visualization*
