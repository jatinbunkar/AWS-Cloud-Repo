<!-- Jatin Bunkar Notes For Simple Notification Service (SNS) --> 
## Simple Notification Service (SNS)

### SNS Simplified:
Simple Notification Service is a pushed-based messaging service that provides a highly scalable, flexible, and cost-effective method to publish a custom messages to subscribers who wish to be informed about a certain topic.

### SNS Key Details:
- SNS is mainly used to send alarms or alerts.
- SNS provides topics for high-throughput, push-based, many-to-many messaging. 
- Using Amazon SNS topics, your publisher systems can fan out messages to a large number of subscriber endpoints for parallel processing, including Amazon SQS queues, AWS Lambda functions, and HTTP/S webhooks. Additionally, SNS can be used to fan out notifications to end users using mobile push, SMS, and email. 
- You can send these push notifications to Apple, Google, Fire OS, and Windows devices.
- SNS allows you to group multiple recipients using topics. A topic is an access point for allowing recipients to dynamically subscribe for identical copies of the same notification.
- One topic can support deliveries to multiple endpoint types. When you publish to a topic, SNS appropriately formats copies of that message to send to whichever kind of device.
- To prevent messages being lost, messages are stored redundantly across multiple AZs.
- There is no long or short polling involved with SNS due to the instantaneous pushing of messages
- SNS has flexible message delivery over multiple transport protocols and has a simple API.
