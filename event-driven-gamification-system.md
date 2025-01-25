`professional experience`

# Implementing an event-driven gamification system that integrated multiple applications

## Presentation

A health-focused company in LATAM provided customizable wellness programs for large corporations, with strong security and data policies. Each program had a set duration, which could be extended. Based on past experience, they saw higher engagement, especially when a program was first launched. Their goal was to increase employee engagement by adding gamification across all platforms. Employees could earn points by interacting with both mobile and desktop systems. These points could be used to track rankings or redeemed for rewards, depending on the program.

## Key Requirements & Quality Attributes

**Multi-Tenancy**  
The system needed to keep data separate for each company to meet regulatory requirements and market demands.

**Scalable Infrastructure**  
It had to handle a large number of users at the same time, especially during peak activity periods.

**Seamless API Integration**  
The system needed to easily connect with existing tools like web apps, mobile apps, and chatbots.

**Performance**  
Employees used a variety of devices, sometimes with poor internet connections, so the system had to work well in all conditions.

**Cost Efficiency**  
The company had a limited budget and a short timeline to test market fit, so the solution had to be affordable and quick to implement.

**Extensibility**  
The system needed to support future growth, making it easy to add user interfaces and integrate with the company’s existing applications.  

## Solution Architecture

To address these challenges, we designed an event-driven gamification system that asynchronously captured and processed user interactions, with all components deployed in the Cloud.

Every user action, regardless of the platform, triggered an event through a unified HTTP-based access point. These events were processed across multiple topics, jobs, and services, with the results ultimately being persisted in the database. 

To ensure that other applications could access updated information without directly querying heavy resources like the database, snapshots were cached and uploaded to storage, enabling them to pull the latest data as needed.

## Outcome

**Quick Integration**  
With an API for communicating with the gamification system, the team quickly integrated gamification features across multiple apps.

**Cost-Effective High Availability**  
By caching data in Cloud Storage, we ensured high availability without incurring additional server or database costs. This approach may seem unusual, but it was driven by both budget and time constraints.

**Delivery Speed**  
A decentralized architecture allowed us to assign specific tasks to different services, enabling parallel development and accelerating the overall delivery process.

**Debugging Challenges**  
The decentralized approach, combined with a variety of topics, made debugging more complex. This could be improved with enhanced observability tools.

**Architecture Complexity**  
With too many components, onboarding new team members could become difficult as the company scales. This can be mitigated with comprehensive and clear documentation.

## Knowledge & Technologies

- Event-Driven Architecture
- Google Cloud Pub/sub
- Google Cloud Function
- Google Cloud Run
- Google Cloud Storage
- MySQL
- Ruby
- Ruby on Rails
