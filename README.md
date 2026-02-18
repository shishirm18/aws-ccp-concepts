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
