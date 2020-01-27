# Design an Event-driven Architecture on Azure - Student guide

## Abstract and learning objetives

In this whiteboard design session, you will work with a group to design a solution for a customer that leverages aspects of event-driven architectures. In the end you will design a solution that meets their needs and will provide them with a unified pipeine for their website, business units and customers.

At the end of this whiteboard design session, you will have gained insight on how best to take advantage of Azure messaging services for designing a highly scalable and cost-effective solution.

## Step 1: Review the customer case study

**Outcome**

Analyze your customer's needs.

Timeframe: 15 minutes

Directions: With all participants in the session, the facilitator/SME presents an overview of the customer case study along with technical tips.

1. Meet your table participants and trainer.
2. Read all of the directions for steps 1-3 in the student guide.
3. As a table team, review the following customer case study.

### Customer situation

Contoso provides an eCommerce web site for their customers. It averages about 10 million clicks a day

They have a ‘recently viewed’ feature on the site that is critical to their business and revenue

Most of their systems rely on batch processing

They are concerned about the amount of time it takes to react to changes and apply updates to their business

Contoso is confident that most of their processing can be done in near-real time

The ‘recently viewed’ functionality takes a long time to process and has many issues

Today, a point-to-point architecture is heavily used throughout Contoso

Directors want to explore the notion of an event-driven architecture and see if there are long-term performance and costs benefits

They would like to add new features to the website (recommendations, trends, etc.)

### Customer needs

Unified pipeline platform

Near-real time processing

- Product changes (example: change data capture)
- Analytics (anomaly detection, trends, etc.)

Provide support for batch processing where necessary

Scalable solution that can handle unexpected demand

Strong preference towards managed services and serverless technologies

Support different types of producers and consumers

Embrace OSS tools and ecosystem

### Customer use cases

**Analytics**  
Contoso would like to support near-real time analytics so that they could:

- Identify trends 
- Catch anomalies
- Enhance recommendations

**Real time updates**
Products updates

- Currently stored in Cosmos DB
- Would like to reflect changes immediately on website (and elsewhere)

Customer and product feedback

- Share updates from 3rd party sources

**Partner notifications**

Notify partners of product changes through some form of publish and subscribe (pub/sub) mechanism.

Partners can provide an endpoint (example: WebHook) to receive relevant updates.

### Customer objections

- Can we have a consistent format for all the events and messages?

- What about business continuity (disaster recovery)?

- Can we replicate the data to another region?

- We need a way to continue to support our batch jobs within this new architecture. Ideally, we’d like to incorporate it into an event-driven architecture. Is this possible?

## Step 2: Design a proof of concept solution

**Outcome**

Design a solution and prepare to present the solution to the target customer audience in a 15-minute chalk-talk format.

Timeframe: 60 minutes

Business needs

Directions: With all participants at your table, answer the following questions and list the answers on a flip chart:

-  Who should you present this solution to? Who is your target customer audience? Who are the decision makers?

- What customer business needs do you need to address with your solution?

**Design**

Directions: With all participants at your table, respond to the following questions on a flip chart:

_High-level architecture_

1. Diagram your initial vision for handling the top-level requirements for the event-driven architecture.

_Batch processing_

TODO: add content

_Partner notifications_

TODO: add content

**Prepare**

Directions: With all participants at your table:

1. Identify any customer needs that are not addressed with the proposed solution.

2. Identify the benefits of your solution.

3. Determine how you will respond to the customer's objections.

Prepare a 15-minute chalk-talk style presentation to the customer.

## Step 3: Present the solution

*Outcome**

Present a solution to the target customer audience in a 15-minute chalk-talk format.

Timeframe: 30 minutes

**Presentation**

Directions:

1. Pair with another table.
2. One table is the design team and the other table is the customer.
3. The design team presents their proposed solution to the customer.
4. The customer makes one of the objections from the list of objections.
5. The design team responds to the objection.
6. The customer team gives feedback to the Microsoft team.
7. Tables switch roles and repeat Steps 2-6.

## Wrap up

Timeframe: 15 minutes

Directions: Tables reconvene with the larger group to hear the facilitator/SME share the preferred solution for the case study.

## Additional references

|                                                              |                                                                                                                           |
| ------------------------------------------------------------ | :------------------------------------------------------------------------------------------------------------------------ |
| **Description**                                              |                                                         **Links**                                                         |
| Compare messaging services                                   | https://docs.microsoft.com/en-us/azure/event-grid/compare-messaging-services                                              |
| Introduction to Azure Event Grid                             | https://docs.microsoft.com/en-us/azure/event-grid/overview                                                                |
| Azure Event Hubs Overview                                    | https://docs.microsoft.com/en-us/azure/event-hubs/event-hubs-about                                                        |
| Event Hubs for Kafka                                         | https://docs.microsoft.com/en-us/azure/event-hubs/event-hubs-for-kafka-ecosystem-overview                                 |
| Event Hubs Capture                                           | https://docs.microsoft.com/en-us/azure/event-hubs/event-hubs-capture-overview                                             |
| Azure Service Bus Overview                                   | https://docs.microsoft.com/en-us/azure/service-bus-messaging/service-bus-messaging-overview                               |
| Azure Stream Analytics Overview                              | https://docs.microsoft.com/en-us/azure/stream-analytics/stream-analytics-introduction                                     |
| Introduction to Azure Functions                              | https://docs.microsoft.com/en-us/azure/azure-functions/functions-overview                                                 |
| What is Logic Apps?                                          | https://docs.microsoft.com/en-us/azure/azure-functions/functions-overview                                                 |
| Azure Cosmos DB + Azure Functions                            | https://docs.microsoft.com/azure/cosmos-db/serverless-computing-database                                                  |
| CloudEvents                                                  | https://cloudevents.io/                                                                                                   |


