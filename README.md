# Design an Event-driven Architecture on Azure - Student guide

## Abstract and learning objetives

In this whiteboard design session, you will work with a group to design a customer solution that leverages aspects of event-driven architectures. This solution should meet their needs and provide them with a unified data pipeine for their website, business units and customers.

At the end of this whiteboard design session, you will have gained insight on how to design highly scalable, cost-effective solutions that leverage Azure messaging services.

## Step 1: Review the customer case study

**Outcome**

Analyze your customer's needs.

Timeframe: 15 minutes

Directions: With all participants in the session, the facilitator/SME will present an overview of the customer case study along with technical tips.

1. Meet your table participants and trainer.
2. Read all of the directions for steps 1-3 in the student guide.
3. As a table team, review the following customer case study.

### Customer situation

Contoso provides an eCommerce web site for their customers that averages approximately 10 million clicks a day.

They have a ‘recently viewed’ feature on the site that is critical to their business and revenue. The ‘recently viewed’ functionality takes a long time to process and has many issues. It leverages cookies, has issues with private browsing and only updates twice a day.

Most of their systems rely on batch processing; they have raised concerns regard the amount of time it takes to react to changes and apply updates to their business. Contoso is confident that most of their processing can be done in near-real time.

Today, a point-to-point architecture is heavily used throughout Contoso. As you can imagine, this approach has become difficult to maintain over the years. While a point-to-point architecture might work for small solutions, Contoso needs a more elegant and flexible solution moving forward.

Directors at Contoso are interested in exploring the notion of an event-driven architecture to see if there are long-term performance and costs benefits to the approach. If they can pull this off, they would like to add new features to the website (recommendations, trends, etc.)

### Customer needs

Some of the main needs for Contoso are:

* **Near real time processing**
  * Product change updates - changes that originate from one system can be reflected in others, in near real time. 
  * Analytics - this includes being able to detect trends and anomalies from traffic on the website. 

* **Provide support for batch processing where necessary**. While they are moving away from batch processing, there will still be a need to keep some operations around that run in batches.

* **Scalable solution that can handle unexpected demand**. They would like to put a solution in place that has the ability to scale for them if necessary. They don't anticipate this happening often, but would like to plan for the possibility.

* **Strong preference towards managed services and serverless technologies**. They are hoping that their new solution will take advantage of managed services as much as possible so that they can focus on their business code, logic and operations.

* **Support different types of producers and consumers**. Contoso has a large ecosystem of applications and tools throughout the organization. The new solution needs to have the ability to integrate well with this existing solutions.

* **Embrace OSS tools and ecosystem**. Integrating with open source tools and frameworks is very important to Contoso. 

* **Unified pipeline platform**. This all comes down to the integration of a common, unified pipeline that can be leveraged by their applications.

### Customer use cases

**Analytics**

Contoso would like to support near-real time analytics so that they can:

* Identify trends
* Catch anomalies
* Provide enhanced recommendations

**Real time updates**

Products updates. Changes to products and other artifacts in the Contoso ecosystem can orginate from multiple sources, including databases. It's important that these change are available to other systems.

* Product information is currently stored in Cosmos DB
* Would like to reflect changes immediately on their website (and elsewhere)

Customer and product feedback. Contoso provides a set of APIs to their partners; both customer and product feedback is shared through these APIs and will be important to many internal consumers.

* Share updates from 3rd party sources

**Partner notifications**

Notify partners of product changes through some form of publish and subscribe (pub/sub) mechanism. Partners can provide an endpoint (example: WebHook) through which they can receive relevant updates and/or subscribe to the updates that are important to them.

### Customer objections

* Can we have a consistent format for all the events and messages?

* What about business continuity (disaster recovery)?

* Can we replicate the data to another region?

* We need a way to continue to support our batch jobs within this new architecture. Ideally, we’d like to incorporate it into an event-driven architecture. Is this possible?

## Step 2: Design a proof of concept solution

**Outcome**

Design a solution and prepare a 15-minute chalk-talk to present the solution to the target customer audience.

Timeframe: 60 minutes

Business needs

Directions: With all participants at your table, answer the following questions and list the answers on a flip chart:

* Who should you present this solution to? Who is your target customer audience? Who are the decision makers?

* What customer business needs do you need to address with your solution?

**Design**

Directions: With all participants at your table, respond to the following questions/tasks on a flip chart:

_High-level architecture_

1. Diagram your initial vision for handling the top-level requirements for the event-driven architecture.

2. Based on the customer situation, what core services would you propose as part of the new event-driven architecture?

_Batch processing_

1. Illustrate how batch processing would be supported within the architecture. 

2. Describe how batch processing can still leverage an event-driven approach.

_Partner notifications_

1. Describe how partners can be notified of important changes from Contoso. 

2. Show the services that will be leveraged to enable partner notifications. 

**Prepare**

Directions: With all participants at your table:

1. Identify any customer needs that are not addressed within the proposed solution.

2. Identify the benefits of your solution.

3. Determine how you will respond to the customer's objections.

Prepare a 15-minute, chalk-talk style presentation for the customer.

## Step 3: Present the solution

**Outcome**

Present a 15-minute chalk-talk on the solution to the target customer audience.

Timeframe: 30 minutes

**Presentation**

Directions:

1. Pair with another table.
2. One table is the design team and the other table is the customer.
3. The design team presents their proposed solution to the customer.
4. The customer makes one of the objections from the list of objections.
5. The design team responds to the objection.
6. The customer team gives feedback to the design team.
7. Tables switch roles and repeat Steps 2-6.

## Wrap up

Timeframe: 15 minutes

Directions: Tables reconvene with the larger group to hear the facilitator/SME share the preferred solution for the case study.

## Additional references

|                                                              |                                                                                                                             |
| ------------------------------------------------------------ | :-------------------------------------------------------------------------------------------------------------------------- |
| **Description**                                              |                                                         **Links**                                                           |
| Compare messaging services                                   | <https://docs.microsoft.com/en-us/azure/event-grid/compare-messaging-services>                                              |
| Introduction to Azure Event Grid                             | <https://docs.microsoft.com/en-us/azure/event-grid/overview>                                                                |
| Azure Event Hubs Overview                                    | <https://docs.microsoft.com/en-us/azure/event-hubs/event-hubs-about>                                                        |
| Event Hubs for Kafka                                         | <https://docs.microsoft.com/en-us/azure/event-hubs/event-hubs-for-kafka-ecosystem-overview>                                 |
| Event Hubs Capture                                           | <https://docs.microsoft.com/en-us/azure/event-hubs/event-hubs-capture-overview>                                             |
| Azure Service Bus Overview                                   | <https://docs.microsoft.com/en-us/azure/service-bus-messaging/service-bus-messaging-overview>                               |
| Azure Stream Analytics Overview                              | <https://docs.microsoft.com/en-us/azure/stream-analytics/stream-analytics-introduction>                                     |
| Introduction to Azure Functions                              | <https://docs.microsoft.com/en-us/azure/azure-functions/functions-overview>                                                 |
| What is Logic Apps?                                          | <https://docs.microsoft.com/en-us/azure/logic-apps/logic-apps-overview>                                                     |
| Azure Cosmos DB + Azure Functions                            | <https://docs.microsoft.com/azure/cosmos-db/serverless-computing-database>                                                  |
| CloudEvents                                                  | <https://cloudevents.io/>                                                                                                   |
