# Architectural Kata: Spring 2023: Road Warrior
![logo](/resources/konttilonkero.png)

## Introduction
This document describes a solution proposal for O'Reilly Architecture Katas 2023 called Road Warrior.

## Members
- Jani Rotola-Pukkila
- Joonas Pessi
- Jussi Haapanen
- Markus Salmi
- Mika Koikkalainen 

## Problem Analysis / Business Case

### Goal

Design an online trip management dashboard to allow travellers to see all of their existing reservations organised by trip either online (web) or through their mobile device.
2 million active users/week
total users: 15 million (user accounts)

### Business requirements

- Poll email looking for travel-related emails
- Filter and whitelist certain emails
- The system must interface with the agency’s existing airline, hotel, and car rental interface system to update travel details (delays, cancellations, updates, gate changes, etc.).
- Updates must be in the app within 5 minutes of an update (better than the competition)
- Customers should be able to add, update, or delete existing reservations manually as well.
- Items in the dashboard should be able to be grouped by trip, and once the trip is complete, the items should automatically be removed from the dashboard.
- Users should also be able to share their trip information by interfacing with standard social media sites or allowing targeted people to view your trip.
- Richest user interface possible across all deployment platforms
- Provide end-of-year summary reports for users with a wide range of metrics about their travel usage
- Road Warrior gathers analytical data from user’s trips for various purposes - travel trends, locations, airline and hotel vendor preferences, cancellation and update frequency, and so on.

### Additional context

- Must integrate seamlessly with existing travel systems (i.e., SABRE, APOLLO)
- Must integrate with a preferred travel agency for quick problem resolution (help me!)
- must work internationally

### Technical requirements

- Users must be able to access the system at all times (max 5 minutes per month of unplanned downtime)
- Travel updates must be presented in the app within 5 minutes of generation by the source
- Response time from web (800ms) and mobile (First-contentful paint of under 1.4 sec)

## Solution

### Driving characteristics

#### Scalability

With 2 million active users per week and a total of 15 million user accounts,
the system needs to be able to handle a large volume of concurrent events and requests.
The system should be able to scale horizontally to handle the load as it might be quite
expensive to scale vertically by increasing instance sizes.

#### Elasticity

Elasticity is the ability of a system to adapt to changes in demand. 
A service with 2 million active users is likely to experience significant changes in demand, both in terms of the number of users and the amount of traffic generated by those users. 
For example, the service might experience spikes in traffic during peak hours or on holidays. It is important for the service to be able to handle these changes in demand without compromising performance or availability.

Here are some specific benefits of elasticity for a service with 2 million users:
- Improved performance: Elasticity allows you to scale up the resources available to the service during peak traffic times, which can help to improve performance and prevent latency issues.
- Increased availability: Elasticity can help to ensure that the service is always available, even if there is a sudden increase in demand. This is because you can quickly scale up the number of resources available to the service to meet the demand.
- Reduced costs: Elasticity can help to reduce costs by allowing you to only pay for the resources that you need. This is in contrast to a traditional monolithic architecture, where you would need to provision a fixed number of resources, even if you were not using them all.

#### Extensibility

Extensibility is the ability of a system to be modified or extended to accommodate new features or changes. This is important for a service with integrations to multiple systems because it allows the service to adapt to changes in those systems without having to be completely redesigned. It makes integrating new system easy. 

#### Responsiveness
Responsiveness is the ability of a system to respond to requests in a timely manner. This is important for a service with 2 million active users because it ensures that users can interact with the service without having to wait too long.

### Architecture Analysis

Here is an overview of general architecture diagaram

![Architecture](/resources/general_architecture.png)
