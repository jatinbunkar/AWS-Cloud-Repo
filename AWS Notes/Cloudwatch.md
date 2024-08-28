<!-- Jatin Bunkar Notes For Cloudwatch --> 
## CloudWatch

### CloudWatch Simplified:
Amazon CloudWatch is a monitoring and observability service. It provides you with data and actionable insights to monitor your applications, respond to system-wide performance changes, optimize resource utilization, and get a unified view of operational health.

### CloudWatch Key Details:
- CloudWatch collects monitoring and operational data in the form of logs, metrics, and events.
- You can use CloudWatch to detect anomalous behavior in your environments, set alarms, visualize logs and metrics side by side, take automated actions, troubleshoot issues, and discover insights to keep your applications
running smoothly.
- Within the compute domain, CloudWatch can inform you about the health of EC2 instances, Autoscaling Groups, Elastic Load Balancers, and Route53 Health Checks.
Within the storage and content delivery domains, CloudWatch can inform you about the health of EBS Volumes, Storage Gateways, and CloudFront.
- With regards to EC2, CloudWatch can only monitor host level metrics such as CPU, network, disk, and status checks for insights like the health of the underlying hypervisor.
- CloudWatch is *NOT* CloudTrail so it is important to know that only CloudTrail can monitor AWS access for security and auditing reasons. CloudWatch is all about performance. CloudTrail is all about auditing.
- CloudWatch with EC2 will monitor events every 5 minutes by default, but you can have 1 minute intervals if you use Detailed Monitoring.

![Screen Shot 2020-06-17 at 8 16 23 PM](https://user-images.githubusercontent.com/13093517/84963455-71af6a00-b0d7-11ea-8168-15dd791bf000.png)

- You can customize your CloudWatch dashboards for insights.
- There is a multi-platform CloudWatch agent which can be installed on both Linux and Windows-based instances. This agent enables you to select the metrics to be collected, including sub-resource metrics such as per-CPU core. You can use this single agent to collect both system metrics and log files from Amazon EC2 instances and on-premises servers.
- The following metrics are not collected from EC2 instances via CloudWatch:
  - Memory utilization
  - Disk swap utilization
  - Disk space utilization
  - Page file utilization
  - Log collection
- If you need the above information, then you can retrieve it via the official CloudWatch agent or you can create a custom metric and send the data on your own via a custom script.
- CloudWatch's key purpose:
  - Collect metrics
  - Collect logs
  - Collect events
  - Create alarms
  - Create dashboards

### CloudWatch Logs:
- You can use Amazon CloudWatch Logs to monitor, store, and access your log files from Amazon EC2 instances, AWS CloudTrail, Amazon Route 53, and other sources. You can then retrieve the associated log data from CloudWatch Logs.
- It helps you centralize the logs from all of your systems, applications, and AWS services that you use, in a single, highly scalable service.
- You can create log groups so that you join logical units of CloudWatch Logs together.
- You can stream custom log files for further insights.

### CloudWatch Events:
- Amazon CloudWatch Events delivers a near real-time stream of system events that describe changes in AWS resources. 
- You can use events to trigger lambdas for example while using alarms to inform you that something went wrong.

### CloudWatch Alarms:
- CloudWatch alarms send notifications or automatically make changes to the resources you are monitoring based on rules that you define. 
- For example, you can create custom CloudWatch alarms which will trigger notifications such as surpassing a set billing threshold.
- CloudWatch alarms have two states of either `ok` or `alarm`

### CloudWatch Metrics:
- CloudWatch Metrics represent a time-ordered set of data points.
- These basically are a variable you can monitor over time to help tell if everything is okay, e.g. Hourly CPU Utilization.
- CloudWatch Metrics allows you to track high resolution metrics at sub-minute intervals all the way down to per second.

### CloudWatch Dashboards:
- CloudWatch dashboards are customizable home pages in the CloudWatch console that you can use to monitor your resources in a single view
- These dashboards integrate with CloudWatch Metrics and CloudWatch Alarms to create customized views of the metrics and alarms for your AWS resources.
