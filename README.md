# aws-ccp-concepts

## Leveraging Global Infrastructure
### Route 53
Its a Managed Domain Name Service (DNS) service

### CloudFront
Its a Content Delivery Network (CDN)
Improves the read performance by caching the content at different Edge locations.

## Cloud Integrations

### Amazon SQS - Simple Queue Service

#### Whats a Queue?
* If we have a Queue, we have producers send messages into that queue. It could be multiple producers sending messages to the queue. Once they are stored, they can be read by Consumers (polling/requesting from the queue). It can be 1 or more consumers.
* Once they are done processing the request, they will delete the message from the queue.

#### SQS details
* SQS is the AWS Oldest offering (over 10 years old)
* Its fully managed (~ serverless), use to decouple applications
* Messages are deleted after they're read by consumers.
* No limit to how many messages can be in the queue.
* Low latency (<10ms)
* Consumers share the work to read messages & scale horizontally

#### Solution Architecture
* If we have web server with EC2 inst. managed by ASG
* Use SQS Queue to put the requests into the queue
* Then we have Video Processing layer, having EC2 inst. managed by ASG. Here, we can scale the 2nd ASG independently from the 1st(so its called decoupling) and also scaling can happen based on the number of messages in the queue.
*  This gives us best user experience and cost efficiency

#### FIFO Queue
* Messages are read in First In First Out technique.
* Producer send messages and consumers process the messages in order.
