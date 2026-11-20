# Peer-to-Peer Carpooling & Expense Splitter

**Name:** Niharika Mirle
**SRN:** PES2UG24AM105

## Overview

The **Peer-to-Peer Carpooling & Expense Splitter** is a proposed software system that connects Driver Hosts with Rider Commuters who share a compatible commute. It allows drivers to publish rides and riders to search for and request them, checks route compatibility (detour of 1.5 km or less), and calculates each participant's fuel cost share once a carpool is confirmed.

This repository documents the proposed software architecture, component design and architectural justification.

## Architectural Style

The system follows a **Layered Architecture with Modular Components**. The architecture separates user interaction, authentication, ride management, route compatibility, fuel cost sharing, ratings and data persistence.

### Architecture Layers

- **Presentation Layer:** Provides the user interface for Rider Commuters and Driver Hosts.
- **Business / Service Layer:** Handles ride publishing, search, requests, route compatibility, cost sharing and validation.
- **Data Access Layer:** Manages communication between application services and the database.
- **Database Layer:** Stores users, licenses, rides, requests, ratings and travel histories.

## System Components

| Component | Responsibility |
|---|---|
| Presentation / UI | Handles user interactions and displays information. |
| Authentication Component | Validates users, verifies driving licenses and manages access control. |
| Ride Management Component | Handles ride publishing, search, requests, Driver Host accept/reject decisions and ride completion. |
| Rating & History Component | Records participant ratings and travel histories. |
| Route Compatibility Service | Uses the external Route/Map Service to calculate the detour and permits matches only within 1.5 km. |
| Fuel Cost Share Service | Calculates each participant's fuel cost share after a carpool is confirmed. |
| Persistence / Database | Stores and retrieves system information with encrypted backups. |

## Component Architecture

The component diagram illustrates the interaction between the system components, including authentication, ride management, route compatibility, fuel cost sharing, ratings and database operations.

![Component Diagram](component_diagram.png)

## Architectural Justification

Layered Architecture was selected because it provides separation of concerns, modularity and maintainability.

- **Separation of Concerns:** Each layer is responsible for a specific part of the system.
- **Maintainability:** The matching rule or cost-splitting formula can be changed without modifying the UI.
- **Security:** Authentication, license verification and protection of sensitive data can be handled centrally.
- **Reliability:** Route compatibility checks and transactional confirmation help prevent incompatible or unaccepted carpools.
- **Extensibility:** A different map provider or a new cost-sharing policy can be added as the system evolves.

## Quality Attributes

| Quality Attribute | Design Approach |
|---|---|
| Security | Authentication, role-based access control, and encrypted storage and backups for ratings, license documents and travel histories. |
| Reliability | Detour validation and transaction-based confirmation of carpools. |
| Maintainability | Modular components and separation of layers. |
| Performance | Route compatibility and matching results within 3 seconds for at least 95% of requests under normal load. |
| Usability | Clear compatible rides, request status and fuel cost share display. |
| Scalability | Modular design that can be extended with additional functionality. |

## Architecture Documentation

- [Architecture Justification](architecture-justification.pdf)
- [Component Diagram](component_diagram.png)

## Project Scope

This repository contains the architectural design and documentation for the Peer-to-Peer Carpooling & Expense Splitter as part of the Software Engineering Laboratory.

The architecture represents a proposed design based on the identified system requirements and use cases.

---

**Software Engineering Laboratory – Lab 3: Component Modelling & Architectural Pattern Selection**
