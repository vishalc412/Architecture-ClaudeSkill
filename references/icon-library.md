# Draw.io Icon Library Reference

This reference contains all technology-specific icons and shapes for professional architecture diagrams.

---

## CRITICAL: Using Draw.io Shape Libraries

Draw.io has built-in shape libraries for AWS, Azure, GCP, Kubernetes, and more. When generating diagrams, use these proper shapes instead of generic rectangles.

---

## AWS Icons

### Compute

```xml
<!-- EC2 Instance -->
<mxCell id="aws-ec2" value="EC2" style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=#F78E04;gradientDirection=north;fillColor=#D05C17;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.ec2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>

<!-- Lambda Function -->
<mxCell id="aws-lambda" value="Lambda" style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=#F78E04;gradientDirection=north;fillColor=#D05C17;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.lambda;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>

<!-- ECS -->
<mxCell id="aws-ecs" value="ECS" style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=#F78E04;gradientDirection=north;fillColor=#D05C17;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.ecs;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>

<!-- EKS (Kubernetes) -->
<mxCell id="aws-eks" value="EKS" style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=#F78E04;gradientDirection=north;fillColor=#D05C17;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.eks;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

### Storage

```xml
<!-- S3 Bucket -->
<mxCell id="aws-s3" value="S3" style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=#60A337;gradientDirection=north;fillColor=#277116;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.s3;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>

<!-- RDS Database -->
<mxCell id="aws-rds" value="RDS" style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=#4D72F3;gradientDirection=north;fillColor=#3334B9;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.rds;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>

<!-- DynamoDB -->
<mxCell id="aws-dynamodb" value="DynamoDB" style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=#4D72F3;gradientDirection=north;fillColor=#3334B9;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.dynamodb;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>

<!-- ElastiCache (Redis) -->
<mxCell id="aws-elasticache" value="ElastiCache" style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=#4D72F3;gradientDirection=north;fillColor=#3334B9;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.elasticache;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

### Networking

```xml
<!-- API Gateway -->
<mxCell id="aws-apigateway" value="API Gateway" style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=#945DF2;gradientDirection=north;fillColor=#5A30B5;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.api_gateway;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>

<!-- CloudFront -->
<mxCell id="aws-cloudfront" value="CloudFront" style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=#945DF2;gradientDirection=north;fillColor=#5A30B5;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.cloudfront;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>

<!-- Load Balancer (ALB/ELB) -->
<mxCell id="aws-elb" value="Load Balancer" style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=#945DF2;gradientDirection=north;fillColor=#5A30B5;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.elastic_load_balancing;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>

<!-- VPC -->
<mxCell id="aws-vpc" value="VPC" style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=#945DF2;gradientDirection=north;fillColor=#5A30B5;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.vpc;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

### Messaging

```xml
<!-- SQS -->
<mxCell id="aws-sqs" value="SQS" style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=#FF4F8B;gradientDirection=north;fillColor=#BC1356;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.sqs;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>

<!-- SNS -->
<mxCell id="aws-sns" value="SNS" style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=#FF4F8B;gradientDirection=north;fillColor=#BC1356;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.sns;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>

<!-- EventBridge -->
<mxCell id="aws-eventbridge" value="EventBridge" style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=#FF4F8B;gradientDirection=north;fillColor=#BC1356;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.eventbridge;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

### AWS Group Containers

```xml
<!-- AWS Cloud Container -->
<mxCell id="aws-cloud" value="AWS Cloud" style="sketch=0;outlineConnect=0;gradientColor=none;html=1;whiteSpace=wrap;fontSize=12;fontStyle=0;shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_aws_cloud;strokeColor=#AAB7B8;fillColor=none;verticalAlign=top;align=left;spacingLeft=30;fontColor=#AAB7B8;dashed=0;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="600" height="400" as="geometry"/>
</mxCell>

<!-- VPC Container -->
<mxCell id="aws-vpc-group" value="VPC" style="sketch=0;outlineConnect=0;gradientColor=none;html=1;whiteSpace=wrap;fontSize=12;fontStyle=0;shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_vpc;strokeColor=#879196;fillColor=none;verticalAlign=top;align=left;spacingLeft=30;fontColor=#879196;dashed=0;" vertex="1" parent="1">
  <mxGeometry x="120" y="150" width="500" height="300" as="geometry"/>
</mxCell>

<!-- Private Subnet -->
<mxCell id="aws-private-subnet" value="Private Subnet" style="sketch=0;outlineConnect=0;gradientColor=none;html=1;whiteSpace=wrap;fontSize=12;fontStyle=0;shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_security_group;strokeColor=#00A4A6;fillColor=#E6F6F7;verticalAlign=top;align=left;spacingLeft=30;fontColor=#147EBA;dashed=0;" vertex="1" parent="1">
  <mxGeometry x="140" y="180" width="200" height="150" as="geometry"/>
</mxCell>

<!-- Public Subnet -->
<mxCell id="aws-public-subnet" value="Public Subnet" style="sketch=0;outlineConnect=0;gradientColor=none;html=1;whiteSpace=wrap;fontSize=12;fontStyle=0;shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_security_group;strokeColor=#7AA116;fillColor=#F2F6E8;verticalAlign=top;align=left;spacingLeft=30;fontColor=#248814;dashed=0;" vertex="1" parent="1">
  <mxGeometry x="380" y="180" width="200" height="150" as="geometry"/>
</mxCell>
```

---

## Kubernetes Icons

```xml
<!-- Kubernetes Cluster -->
<mxCell id="k8s-cluster" value="Kubernetes Cluster" style="sketch=0;html=1;dashed=0;whitespace=wrap;fillColor=#2875E2;strokeColor=#ffffff;points=[[0.005,0.63,0],[0.1,0.2,0],[0.9,0.2,0],[0.995,0.63,0],[0.72,0.99,0],[0.5,1,0],[0.28,0.99,0]];verticalLabelPosition=bottom;align=center;verticalAlign=top;shape=mxgraph.kubernetes.icon;prIcon=master;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="80" height="76" as="geometry"/>
</mxCell>

<!-- Pod -->
<mxCell id="k8s-pod" value="Pod" style="sketch=0;html=1;dashed=0;whitespace=wrap;fillColor=#326CE5;strokeColor=#ffffff;points=[[0.005,0.63,0],[0.1,0.2,0],[0.9,0.2,0],[0.995,0.63,0],[0.72,0.99,0],[0.5,1,0],[0.28,0.99,0]];verticalLabelPosition=bottom;align=center;verticalAlign=top;shape=mxgraph.kubernetes.icon;prIcon=pod;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="60" height="57" as="geometry"/>
</mxCell>

<!-- Deployment -->
<mxCell id="k8s-deployment" value="Deployment" style="sketch=0;html=1;dashed=0;whitespace=wrap;fillColor=#326CE5;strokeColor=#ffffff;points=[[0.005,0.63,0],[0.1,0.2,0],[0.9,0.2,0],[0.995,0.63,0],[0.72,0.99,0],[0.5,1,0],[0.28,0.99,0]];verticalLabelPosition=bottom;align=center;verticalAlign=top;shape=mxgraph.kubernetes.icon;prIcon=deploy;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="60" height="57" as="geometry"/>
</mxCell>

<!-- Service -->
<mxCell id="k8s-service" value="Service" style="sketch=0;html=1;dashed=0;whitespace=wrap;fillColor=#326CE5;strokeColor=#ffffff;points=[[0.005,0.63,0],[0.1,0.2,0],[0.9,0.2,0],[0.995,0.63,0],[0.72,0.99,0],[0.5,1,0],[0.28,0.99,0]];verticalLabelPosition=bottom;align=center;verticalAlign=top;shape=mxgraph.kubernetes.icon;prIcon=svc;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="60" height="57" as="geometry"/>
</mxCell>

<!-- Ingress -->
<mxCell id="k8s-ingress" value="Ingress" style="sketch=0;html=1;dashed=0;whitespace=wrap;fillColor=#326CE5;strokeColor=#ffffff;points=[[0.005,0.63,0],[0.1,0.2,0],[0.9,0.2,0],[0.995,0.63,0],[0.72,0.99,0],[0.5,1,0],[0.28,0.99,0]];verticalLabelPosition=bottom;align=center;verticalAlign=top;shape=mxgraph.kubernetes.icon;prIcon=ing;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="60" height="57" as="geometry"/>
</mxCell>

<!-- ConfigMap -->
<mxCell id="k8s-configmap" value="ConfigMap" style="sketch=0;html=1;dashed=0;whitespace=wrap;fillColor=#326CE5;strokeColor=#ffffff;points=[[0.005,0.63,0],[0.1,0.2,0],[0.9,0.2,0],[0.995,0.63,0],[0.72,0.99,0],[0.5,1,0],[0.28,0.99,0]];verticalLabelPosition=bottom;align=center;verticalAlign=top;shape=mxgraph.kubernetes.icon;prIcon=cm;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="60" height="57" as="geometry"/>
</mxCell>

<!-- Secret -->
<mxCell id="k8s-secret" value="Secret" style="sketch=0;html=1;dashed=0;whitespace=wrap;fillColor=#326CE5;strokeColor=#ffffff;points=[[0.005,0.63,0],[0.1,0.2,0],[0.9,0.2,0],[0.995,0.63,0],[0.72,0.99,0],[0.5,1,0],[0.28,0.99,0]];verticalLabelPosition=bottom;align=center;verticalAlign=top;shape=mxgraph.kubernetes.icon;prIcon=secret;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="60" height="57" as="geometry"/>
</mxCell>

<!-- StatefulSet -->
<mxCell id="k8s-statefulset" value="StatefulSet" style="sketch=0;html=1;dashed=0;whitespace=wrap;fillColor=#326CE5;strokeColor=#ffffff;points=[[0.005,0.63,0],[0.1,0.2,0],[0.9,0.2,0],[0.995,0.63,0],[0.72,0.99,0],[0.5,1,0],[0.28,0.99,0]];verticalLabelPosition=bottom;align=center;verticalAlign=top;shape=mxgraph.kubernetes.icon;prIcon=sts;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="60" height="57" as="geometry"/>
</mxCell>

<!-- Namespace Container -->
<mxCell id="k8s-namespace" value="namespace: production" style="rounded=0;whiteSpace=wrap;html=1;fillColor=none;strokeColor=#326CE5;strokeWidth=2;dashed=1;dashPattern=8 8;verticalAlign=top;align=left;spacingLeft=10;fontSize=12;fontColor=#326CE5;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="400" height="300" as="geometry"/>
</mxCell>
```

---

## Docker Icons

```xml
<!-- Docker Container -->
<mxCell id="docker-container" value="Container" style="sketch=0;html=1;strokeColor=none;fillColor=#0F5FA5;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;align=center;shape=mxgraph.azure.docker;fontSize=12;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="60" height="50" as="geometry"/>
</mxCell>

<!-- Docker Image -->
<mxCell id="docker-image" value="Image" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#0db7ed;strokeColor=#066d9a;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="80" height="50" as="geometry"/>
</mxCell>
```

---

## Framework & Technology Icons

### Frontend

```xml
<!-- React -->
<mxCell id="react" value="React" style="shape=image;html=1;verticalLabelPosition=bottom;verticalAlign=top;imageAspect=0;aspect=fixed;image=https://upload.wikimedia.org/wikipedia/commons/a/a7/React-icon.svg;fontSize=12;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="64" height="57" as="geometry"/>
</mxCell>

<!-- Alternative React (Blue Box) -->
<mxCell id="react-box" value="&lt;b&gt;React&lt;/b&gt;&lt;br&gt;Frontend" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#61DAFB;strokeColor=#21A1C4;fontColor=#1a1a1a;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="120" height="60" as="geometry"/>
</mxCell>

<!-- Vue.js -->
<mxCell id="vue" value="&lt;b&gt;Vue.js&lt;/b&gt;&lt;br&gt;Frontend" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#42b883;strokeColor=#35495e;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="120" height="60" as="geometry"/>
</mxCell>

<!-- Angular -->
<mxCell id="angular" value="&lt;b&gt;Angular&lt;/b&gt;&lt;br&gt;Frontend" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#DD0031;strokeColor=#C3002F;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="120" height="60" as="geometry"/>
</mxCell>

<!-- Next.js -->
<mxCell id="nextjs" value="&lt;b&gt;Next.js&lt;/b&gt;&lt;br&gt;Frontend" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#000000;strokeColor=#333333;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="120" height="60" as="geometry"/>
</mxCell>
```

### Backend

```xml
<!-- Node.js -->
<mxCell id="nodejs" value="&lt;b&gt;Node.js&lt;/b&gt;&lt;br&gt;API" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#339933;strokeColor=#2d862d;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="120" height="60" as="geometry"/>
</mxCell>

<!-- Python -->
<mxCell id="python" value="&lt;b&gt;Python&lt;/b&gt;&lt;br&gt;FastAPI" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#3776AB;strokeColor=#2d5f8a;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="120" height="60" as="geometry"/>
</mxCell>

<!-- Java/Spring Boot -->
<mxCell id="spring" value="&lt;b&gt;Spring Boot&lt;/b&gt;&lt;br&gt;Java" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#6DB33F;strokeColor=#5a9934;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="120" height="60" as="geometry"/>
</mxCell>

<!-- Go -->
<mxCell id="golang" value="&lt;b&gt;Go&lt;/b&gt;&lt;br&gt;Service" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#00ADD8;strokeColor=#0091b5;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="120" height="60" as="geometry"/>
</mxCell>

<!-- .NET -->
<mxCell id="dotnet" value="&lt;b&gt;.NET&lt;/b&gt;&lt;br&gt;C# API" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#512BD4;strokeColor=#4024a8;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="120" height="60" as="geometry"/>
</mxCell>
```

### Databases

```xml
<!-- PostgreSQL -->
<mxCell id="postgresql" value="&lt;b&gt;PostgreSQL&lt;/b&gt;" style="shape=cylinder3;whiteSpace=wrap;html=1;boundedLbl=1;backgroundOutline=1;size=15;fillColor=#336791;strokeColor=#2d5a7d;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="100" height="80" as="geometry"/>
</mxCell>

<!-- MySQL -->
<mxCell id="mysql" value="&lt;b&gt;MySQL&lt;/b&gt;" style="shape=cylinder3;whiteSpace=wrap;html=1;boundedLbl=1;backgroundOutline=1;size=15;fillColor=#4479A1;strokeColor=#3a6a8a;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="100" height="80" as="geometry"/>
</mxCell>

<!-- MongoDB -->
<mxCell id="mongodb" value="&lt;b&gt;MongoDB&lt;/b&gt;" style="shape=cylinder3;whiteSpace=wrap;html=1;boundedLbl=1;backgroundOutline=1;size=15;fillColor=#47A248;strokeColor=#3d8a3d;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="100" height="80" as="geometry"/>
</mxCell>

<!-- Redis -->
<mxCell id="redis" value="&lt;b&gt;Redis&lt;/b&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#DC382D;strokeColor=#b52e25;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="100" height="60" as="geometry"/>
</mxCell>

<!-- Elasticsearch -->
<mxCell id="elasticsearch" value="&lt;b&gt;Elasticsearch&lt;/b&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#FEC514;strokeColor=#d4a511;fontColor=#1a1a1a;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="120" height="60" as="geometry"/>
</mxCell>
```

### Messaging

```xml
<!-- Kafka -->
<mxCell id="kafka" value="&lt;b&gt;Apache Kafka&lt;/b&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#231F20;strokeColor=#000000;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="120" height="60" as="geometry"/>
</mxCell>

<!-- RabbitMQ -->
<mxCell id="rabbitmq" value="&lt;b&gt;RabbitMQ&lt;/b&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#FF6600;strokeColor=#cc5200;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="120" height="60" as="geometry"/>
</mxCell>
```

---

## Microservice Component Shapes

### Service Box (Standardized)

```xml
<!-- Microservice Template -->
<mxCell id="microservice-template" value="" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#1a1a2e;strokeColor=#16213e;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="140" height="80" as="geometry"/>
</mxCell>

<!-- Service Icon (inside service box) -->
<mxCell id="service-icon" value="⚙️" style="text;html=1;strokeColor=none;fillColor=none;align=center;verticalAlign=middle;fontSize=24;" vertex="1" parent="microservice-template">
  <mxGeometry x="10" y="15" width="30" height="30" as="geometry"/>
</mxCell>

<!-- Service Name -->
<mxCell id="service-name" value="&lt;b&gt;Order Service&lt;/b&gt;&lt;br&gt;&lt;font color='#888888' size='2'&gt;Node.js&lt;/font&gt;" style="text;html=1;strokeColor=none;fillColor=none;align=left;verticalAlign=middle;fontSize=12;fontColor=#ffffff;" vertex="1" parent="microservice-template">
  <mxGeometry x="45" y="15" width="90" height="50" as="geometry"/>
</mxCell>
```

### API Gateway

```xml
<mxCell id="api-gateway" value="&lt;b&gt;API Gateway&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;Kong / nginx&lt;/font&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#5C4D7D;strokeColor=#4a3d68;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="140" height="60" as="geometry"/>
</mxCell>
```

### Load Balancer

```xml
<mxCell id="load-balancer" value="&lt;b&gt;Load Balancer&lt;/b&gt;" style="shape=hexagon;perimeter=hexagonPerimeter2;whiteSpace=wrap;html=1;fixedSize=1;fillColor=#4ECDC4;strokeColor=#3dbdb4;fontColor=#1a1a1a;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="120" height="60" as="geometry"/>
</mxCell>
```

---

## User/Client Icons

```xml
<!-- User/Person -->
<mxCell id="user" value="User" style="shape=umlActor;verticalLabelPosition=bottom;verticalAlign=top;html=1;outlineConnect=0;fillColor=#f8cecc;strokeColor=#b85450;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="40" height="80" as="geometry"/>
</mxCell>

<!-- Mobile App -->
<mxCell id="mobile-app" value="&lt;b&gt;Mobile App&lt;/b&gt;&lt;br&gt;iOS / Android" style="shape=mxgraph.ios7.icons.smartphone;html=1;whiteSpace=wrap;strokeWidth=2;strokeColor=#666666;fillColor=#f5f5f5;labelPosition=center;verticalLabelPosition=bottom;verticalAlign=top;fontSize=12;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="32" height="56" as="geometry"/>
</mxCell>

<!-- Web Browser -->
<mxCell id="web-browser" value="&lt;b&gt;Web Browser&lt;/b&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#ffffff;strokeColor=#666666;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="120" height="60" as="geometry"/>
</mxCell>

<!-- External System -->
<mxCell id="external-system" value="&lt;b&gt;External API&lt;/b&gt;&lt;br&gt;Third-party" style="ellipse;shape=cloud;whiteSpace=wrap;html=1;fillColor=#fff2cc;strokeColor=#d6b656;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="140" height="80" as="geometry"/>
</mxCell>
```

---

## Connector Styles

### Standard Connectors

```xml
<!-- Solid Arrow (Synchronous) -->
<mxCell id="conn-sync" value="HTTP/REST" style="endArrow=classic;html=1;rounded=0;strokeWidth=2;strokeColor=#333333;fontSize=11;labelBackgroundColor=#ffffff;fontColor=#333333;" edge="1" parent="1" source="source" target="target">
  <mxGeometry relative="1" as="geometry"/>
</mxCell>

<!-- Dashed Arrow (Async/Event) -->
<mxCell id="conn-async" value="Event" style="endArrow=classic;html=1;rounded=0;strokeWidth=2;strokeColor=#d97706;fontSize=11;labelBackgroundColor=#ffffff;fontColor=#d97706;dashed=1;dashPattern=8 8;" edge="1" parent="1" source="source" target="target">
  <mxGeometry relative="1" as="geometry"/>
</mxCell>

<!-- Bidirectional -->
<mxCell id="conn-bidirectional" value="WebSocket" style="endArrow=classic;startArrow=classic;html=1;rounded=0;strokeWidth=2;strokeColor=#059669;fontSize=11;labelBackgroundColor=#ffffff;fontColor=#059669;" edge="1" parent="1" source="source" target="target">
  <mxGeometry relative="1" as="geometry"/>
</mxCell>
```

---

## Container/Grouping Styles

```xml
<!-- System Boundary -->
<mxCell id="system-boundary" value="&lt;b&gt;System Name&lt;/b&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=none;strokeColor=#666666;strokeWidth=2;dashed=1;dashPattern=8 8;verticalAlign=top;align=left;spacingLeft=10;fontSize=14;fontColor=#666666;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="500" height="400" as="geometry"/>
</mxCell>

<!-- Layer Container -->
<mxCell id="layer" value="&lt;b&gt;Presentation Layer&lt;/b&gt;" style="swimlane;whiteSpace=wrap;html=1;fillColor=#f5f5f5;strokeColor=#666666;strokeWidth=2;fontStyle=1;fontSize=14;startSize=30;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="600" height="200" as="geometry"/>
</mxCell>

<!-- Microservices Group -->
<mxCell id="microservices-group" value="Microservices" style="rounded=0;whiteSpace=wrap;html=1;fillColor=#e8f4ea;strokeColor=#82b366;strokeWidth=2;verticalAlign=top;align=left;spacingLeft=10;fontSize=12;fontColor=#2d5016;fontStyle=1;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="400" height="250" as="geometry"/>
</mxCell>
```

---

## Color Reference

### By Technology

| Technology | Fill Color | Stroke Color |
|-----------|-----------|--------------|
| React | `#61DAFB` | `#21A1C4` |
| Vue.js | `#42b883` | `#35495e` |
| Angular | `#DD0031` | `#C3002F` |
| Node.js | `#339933` | `#2d862d` |
| Python | `#3776AB` | `#2d5f8a` |
| Java/Spring | `#6DB33F` | `#5a9934` |
| Go | `#00ADD8` | `#0091b5` |
| .NET | `#512BD4` | `#4024a8` |
| PostgreSQL | `#336791` | `#2d5a7d` |
| MongoDB | `#47A248` | `#3d8a3d` |
| Redis | `#DC382D` | `#b52e25` |
| Kafka | `#231F20` | `#000000` |
| Docker | `#0db7ed` | `#066d9a` |
| Kubernetes | `#326CE5` | `#2759bf` |

### AWS Color Palette

| Service Category | Fill Gradient Start | Fill Gradient End |
|-----------------|--------------------|--------------------|
| Compute | `#D05C17` | `#F78E04` |
| Storage | `#277116` | `#60A337` |
| Database | `#3334B9` | `#4D72F3` |
| Networking | `#5A30B5` | `#945DF2` |
| Integration | `#BC1356` | `#FF4F8B` |

---

## Quick Copy Templates

### Complete Microservice

```xml
<!-- Auth Service -->
<mxCell id="auth-service" value="&lt;b&gt;Auth Service&lt;/b&gt;&lt;br&gt;&lt;font color='#888888' size='2'&gt;Node.js + JWT&lt;/font&gt;" style="rounded=1;whiteSpace=wrap;html=1;fillColor=#339933;strokeColor=#2d862d;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="140" height="70" as="geometry"/>
</mxCell>
```

### Complete Database

```xml
<!-- Users Database -->
<mxCell id="users-db" value="&lt;b&gt;users_db&lt;/b&gt;&lt;br&gt;&lt;font size='2'&gt;PostgreSQL&lt;/font&gt;" style="shape=cylinder3;whiteSpace=wrap;html=1;boundedLbl=1;backgroundOutline=1;size=15;fillColor=#336791;strokeColor=#2d5a7d;fontColor=#ffffff;fontSize=12;strokeWidth=2;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="100" height="80" as="geometry"/>
</mxCell>
```

---

*Use these icons and shapes to create professional, technology-specific architecture diagrams.*
