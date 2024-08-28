<!-- Jatin Bunkar Notes For Lambda --> 
## Lambda

### Lambda Simplified:
AWS Lambda lets you run code without provisioning or managing servers. You pay only for the compute time you consume. With Lambda, you can run code for virtually any type of application or backend service - all with zero administration. You upload your code and Lambda takes care of everything required to run and scale your code with high availability. You can set up your code to be automatically triggered from other AWS services or be called directly from any web / mobile app.

### Lambda Key Details:
- Lambda is a compute service where you upload your code as a function and AWS provisions the necessary details underneath the function so that the function executes successfully. 
- AWS Lambda is the ultimate abstraction layer. You only worry about code, AWS does everything else.
- Lambda supports Go, Python, C#, PowerShell, Node.js, and Java
- Each Lambda function maps to one request. Lambda scales horizontally automatically.
- Lambda is priced on the number of requests and the first one million are free. Each million afterwards is $0.20.
- Lambda is also priced on the runtime of your code, rounded up to the nearest 100mb, and the amount of memory your code allocates.
- Lambda works globally.
- Lambda functions can trigger other Lambda functions.
- You can use Lambda as an event-driven service that executes based on changes in your AWS ecosystem.
- You can also use Lambda as a handler in response to HTTP events via API calls over the AWS SDK or API Gateway.

![Screen Shot 2020-06-30 at 9 19 33 AM](https://user-images.githubusercontent.com/13093517/86130894-df35a000-bab2-11ea-9908-acbe3e8d4824.png)

- When you create or update Lambda functions that use environment variables, AWS Lambda encrypts them using the AWS Key Management Service. When your Lambda function is invoked, those values are decrypted and made available to the Lambda code.
- The first time you create or update Lambda functions that use environment variables in a region, a default service key is created for you automatically within AWS KMS. This key is used to encrypt environment variables. However, if you wish to use encryption helpers and use KMS to encrypt environment variables after your Lambda function is created, you must create your own AWS KMS key and choose it instead of the default key. 
- To enable your Lambda function to access resources inside a private VPC, you must provide additional VPC-specific configuration information that includes VPC subnet IDs and security group IDs. AWS Lambda uses this information to set up elastic network interfaces (ENIs) that enable your function to connect securely to other resources within a private VPC.

- AWS X-Ray allows you to debug your Lambda function in case of unexpected behavior.


### Lambda@Edge:
- You can use Lambda@Edge to allow your Lambda functions to customize the content that CloudFront delivers.
- It adds compute capacity to your CloudFront edge locations and allows you to execute the functions in AWS locations closer to your application's viewers. The functions run in response to CloudFront events, without provisioning or managing servers. You can use Lambda functions to change CloudFront requests and responses at the following points:
  - After CloudFront receives a request from a viewer (viewer request)
  - Before CloudFront forwards the request to the origin (origin request)
  - After CloudFront receives the response from the origin (origin response)
  - Before CloudFront forwards the response to the viewer (viewer response)
  
![Screen Shot 2020-06-30 at 9 27 48 AM](https://user-images.githubusercontent.com/13093517/86131713-fc1ea300-bab3-11ea-8190-1d13128bee92.png)

- You'd use Lambda@Edge to simplify and reduce origin infrastructure.


## API Gateway

### API Gateway Simplified:
API Gateway is a fully managed service for developers that makes it easy to build, publish, manage, and secure entire APIs. With a few clicks in the AWS Management Console, you can create an API that acts as a “front door” for applications to access data, business logic, or functionality from your back-end services, such as workloads running on EC2) code running on AWS Lambda, or any web application. 

### API Gateway Key Details:
- Amazon API Gateway handles all the tasks involved in accepting and processing up to hundreds of thousands of concurrent API calls, including traffic management, authorization and access control, monitoring, and API version management.
- Amazon API Gateway has no minimum fees or startup costs. You pay only for the API calls you receive and the amount of data transferred out.
- API Gateway does the following for your APIs:
  - Exposes HTTP(S) endpoints for RESTful functionality
  - Uses serverless functionality to connect to Lambda & DynamoDB
  - Can send each API endpoint to a different target
  - Runs cheaply and efficiently
  - Scales readily and effortlessly
  - Can throttle requests to prevent attacks
  - Track and control usage via an API key
  - Can be version controlled
  - Can be connected to CloudWatch for monitoring and observability
- Since API Gateway can function with AWS Lambda, you can run your APIs and code without needing to maintain servers.
- Amazon API Gateway provides throttling at multiple levels including global and by a service call.
  - In software, a throttling process, or a throttling controller as it is sometimes called, is a process responsible for regulating the rate at which application processing is conducted, either statically or dynamically.
  - Throttling limits can be set for standard rates and bursts. For example, API owners can set a rate limit of 1,000 requests per second for a specific method in their REST APIs, and also configure Amazon API Gateway to handle a burst of 2,000 requests per second for a few seconds. 
  - Amazon API Gateway tracks the number of requests per second. Any requests over the limit will receive a 429 HTTP response. The client SDKs generated by Amazon API Gateway retry calls automatically when met with this response.
- You can add caching to API calls by provisioning an Amazon API Gateway cache and specifying its size in gigabytes. The cache is provisioned for a specific stage of your APIs. This improves performance and reduces the traffic sent to your back end. Cache settings allow you to control the way the cache key is built and the time-to-live (TTL) of the data stored for each method. Amazon API Gateway also exposes management APIs that help you invalidate the cache for each stage.
- You can enable API caching for improving latency and reducing I/O for your endpoint.
- When caching for a particular API stage (version controlled version), you cache responses for a particular TTL in seconds.
- API Gateway supports AWS Certificate Manager and can make use of free TLS/SSL certificates.
- With API Gateway, there are two kinds of API calls:
  - Calls to the API Gateway API to create, modify, delete, or deploy REST APIs. These are logged in CloudTrail.
  - API calls set up by the developers to deliver their custom functionality: These are not logged in CloudTrail.


### Cross Origin Resource Sharing:
- In computing, the same-origin policy is an important concept where a web browser permits scripts contained in one page to access data from another page, but only if both pages have the same origin.
- This behavior is enforced by browsers, but is ignored by tools like cURL and PostMan.
- Cross-origin resource sharing (CORS) is one way the server at the origin can relax the same-origin policy. CORS allows sharing of restricted resources like fonts to be requested from another domain outside the original domain of where the first resource was shared from.
- CORS defines a way for client web applications that are loaded in one domain to interact with resources in a different domain. With CORS support, you can build rich client-side web applications with Amazon S3 and selectively allow cross-origin access to your Amazon S3 resources.
- If you ever come across an error that mentions that an origin policy cannot be read at the remote resource, then you need to enable CORS on API Gateway.
- CORS is enforced on the client (web browser) side.
- A common example of this issue is if you are using a site with Javascript/AJAX for multiple domains under API Gateway. You would need to ensure that CORS is enabled.
- CORS does not prevent XSS attacks, but does protect against CSRF attacks. What it does is controls who can use the data served by your endpoint. So if you have a weather website with callbacks to an API that checks the forecast, you could stop someone from writing a website that serves JavaScript calls into your API when they navigate to your website.
- When someone attempts the malicious calls, your browser will read the CORS headers and it will not allow the request to take place thus protecting you from the attack.
