# Architectural Kata: Spring 2023: Road Warrior

## Introduction

## Members

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

#### Extensibility

#### Responsiveness

### Architecture Analysis

Here is an overview of general architecture diagaram

![Architecture](/resources/general_architecture.png)
