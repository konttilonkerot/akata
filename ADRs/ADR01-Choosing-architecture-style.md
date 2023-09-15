# ADR01 architecture style

## Date

2023-09-15

## Status

Active

## Context

The system is a large-scale, distributed system that needs to be able to handle a high volume of events. The system also needs to be highly scalable and fault-tolerant.

## Decision

We decided to use an event-driven architecture for this system. Event-driven architectures are well-suited for handling large volumes of events and for ensuring scalability and fault-tolerance.

## Consequences

The use of an event-driven architecture will have the following consequences

The system will be more loosely coupled, which will make it easier to maintain and evolve.
The system will be more scalable, as new components can be added without affecting the existing components (adding new agencies or other integrations).
The system will be more fault-tolerant, as failures of individual components will not affect the overall system.

## Alternatives

![](/resources/ADR01-Choosing-architecture-style-1.png)

## The alternatives to using an event-driven architecture include

A centralized architecture, where all events are processed by a single component.
A distributed architecture, where events are processed by multiple components.
A centralized architecture would not be scalable or fault-tolerant enough for this system. A distributed architecture would be more scalable and fault-tolerant, but it would be more complex to implement and maintain.

## Decision rationale

We chose to use an event-driven architecture because it is the best solution for the system's requirements of scalability, fault-tolerance, and loose coupling.

## Next steps

## The next steps are to

Design the event-driven architecture in more detail.
Implement the event-driven architecture.
Test the event-driven architecture.
Approvals
This architectural decision was approved by the following stakeholders
John Doe, Architect
Jane Doe, Developer
Susan Smith, QA Engineer
