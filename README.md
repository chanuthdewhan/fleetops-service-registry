# FleetOps - Service Registry

Part of the **FleetOps Fleet & Logistics Dispatch System**, submitted for the
Enterprise Cloud Architecture (ITS 2130) capstone project.

## Student Information
- **Name:** K.D. Chanuth Dewhan
- **Student ID:** 241722017
- **Slack Handle:** @chanuthdewhan
- **GCP Project ID:** fleet-ops-506803

## Project Description
The Eureka-based service registry for the FleetOps platform. Every other
microservice (Config Server, API Gateway, and all business services)
registers itself here on startup, and discovers the other services it needs
to communicate with through this registry rather than hardcoded addresses.
This enables horizontal scaling — new service instances register
automatically and become immediately reachable through the API Gateway's
load-balanced routing.

## Technology Stack
- Java 25
- Spring Boot 4.1
- Spring Cloud 2025.1.2 — Netflix Eureka Server
- Spring Boot Actuator

## Setup / Getting Started

```bash
git clone https://github.com/chanuthdewhan/fleetops-service-registry.git
cd fleetops-service-registry
./mvnw spring-boot:run
```

Runs on port `9001` locally. Once started, the Eureka dashboard is available
at `http://localhost:9001`, listing all currently registered service
instances.

This service has no dependency on Config Server or any other FleetOps
service — it should be the first service started when running the platform
locally.

## Live Deployment
- **GCP Project ID:** fleet-ops-506803
- **Region:** asia-southeast1
- **Deployment model:** IaaS — Compute Engine, managed via PM2