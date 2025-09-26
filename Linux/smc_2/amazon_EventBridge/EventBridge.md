# Amazon EventBridge
- Is a severless event bus that makes it easier to build event-driven applications at scale
using events generated from your applications, integrated Software-as-a-Service (SaaS) Applications,
and services.
- Since it uses events to initiate action on connected applications, it makes it
easier for developers to build applications that are more agile and reliable.
- Allows you to work asynchronously.

### What is an event?
- An event is a record of an action that has happened in the past. In this context, it is 
represented as a JSON object that contains data from the event and metadata about the event.
- Events can come from many different sources and can look very different from each other.

### What is an event bus?
- An event bus can ingest many different events from many different locations. 
- As the events enter the bus, they remain on the bus for a configured period of time.

### How do we use the events in the bus?
- Amazon EventBridge allows you to set up rules. 
- These rules are data patterns that match some or all of the events on a bus. 
- EventBridge evaluates each event against each rule you create. 
- If the rule does not apply, the event is ignored by that rule. If the rule does apply, 
then EventBridge will send a copy of that event to a configured target. 
- Either way, the event remains on the bus to be evaluated by other rules.

## Security & Compliance
- Event-driven architecture is a style of building software that is loosely coupled.
- By using EventBridge, developers can quickly build and deploy applications that are 
more scalable and easier to maintain.

### Centralized auditing and logging
- With EventBridge, you can centrally log events and API calls from various AWS services 
and your applications.

### Fine-grained access controls
- You can set detailed permissions about who can publish events to, and consume events from, 
an event bus for strict access controls.

### Encryption of data in transit and at rest
- EventBridge encrypts all data as it travels between EventBridge services and it encrypts 
data at rest. This helps prevent unauthorized access.

### Compliance with various standards
- EventBridge is compliant with various standards and regulations like SOC, ISO, and PCI 
DSS. This makes it suitable for building compliant applications.

### Integration with CloudTrail
- EventBridge API calls are logged in CloudTrail to provide further auditing visibility.
CloudTrail is widely used for compliance.

### Security monitoring and alerting
- You can detect security incidents and threats by creating rules that match events and 
initiate alerts or actions.

### Serverless
- EventBridge is fully managed and serverless. This removes considerable security and 
compliance burdens related to infrastructure management.
