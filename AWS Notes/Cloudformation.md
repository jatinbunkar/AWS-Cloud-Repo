<!-- Jatin Bunkar Notes For Cloudformation --> 
## CloudFormation

### CloudFormation Simplified:
CloudFormation is an automated tool for provisioning entire cloud-based environments. It is similar to Terraform where you codify the instructions for what you want to have inside your application setup (X many web servers of Y type with a Z type DB on the backend, etc). It makes it a lot easier to just describe what you want in markup and have AWS do the actual provisioning work involved.

### CloudFormation Key Details:
- The main use case for CloudFormation is for advanced setups and production environments as it is complex and has many robust features.
- CloudFormation templates can be used to create, update, and delete infrastructure.
- The templates are written in YAML or JSON
- A full CloudFormation setup is called a stack.
- Once a template is created, AWS will make the corresponding stack. This is the living and active representation of said template. One template can create an infinite number of stacks.
- The *Resources* field is the only mandatory field when creating a CloudFormation template
- Rollback triggers allow you to monitor the creation of the stack as it's built. If an error occurs, you can trigger a rollback as the name implies.
- <a href="https://aws.amazon.com/quickstart/?quickstart-all.sort-by=item.additionalFields.updateDate&quickstart-all.sort-order=desc">AWS Quick Starts is composed of many high-quality CloudFormation stacks designed by AWS engineers.</a>
- An example template that would spin up an EC2 instance:

![Screen Shot 2020-07-01 at 8 44 52 AM](https://user-images.githubusercontent.com/13093517/86245210-27b69180-bb77-11ea-8dff-3d663957a8e2.png)

- For any Logical Resources in the stack, CloudFormation will make a corresponding Physical Resources in your AWS account. It is CloudFormation’s job to keep the logical and physical resources in sync.
- A template can be updated and then used to update the same stack.
