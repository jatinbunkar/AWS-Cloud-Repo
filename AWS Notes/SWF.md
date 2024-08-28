<!-- Jatin Bunkar Notes For Simple Workflow Service (SWF) --> 
## Simple Workflow Service (SWF)

### SWF Simplified:
SWF is a web service that makes it easy to coordinate work across distributed application components. SWF has a range of use cases including media processing, web app backend, business process workflows, and analytical pipelines.

### SWF Key Details:
- SWF is a way of coordinating tasks between application and people. It is a service that combines digital and human-oriented workflows.
- An example of a human-oriented workflow is the process in which Amazon warehouse workers find and ship your item as part of your Amazon order.
- SWF provides a task-oriented API and ensures a task is assigned only once and is never duplicated. Using Amazon warehouse workers as an example again, this would make sense. Amazon wouldn’t want to send you the same item twice as they'd lose money.
- The SWF pipeline is composed of three different worker applications that help to bring a job to completion:
  - SWF Actors are workers that trigger the beginning of a workflow.
  - SWF Deciders are workers that control the flow of the workflow once it's been started.
  - SWF Activity Workers are the workers that actually carry out the task to completion.
- With SWF, workflow executions can last up to one year compared to the 14 days maximum retention period for SQS.
