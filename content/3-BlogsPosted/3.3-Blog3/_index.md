---
title: "Blog 3"
date: 2026-06-23
weight : 1
chapter : false
pre : " <b> 3.3 </b> "
---

# BUILDING MULTI-DEPARTMENT RAG WITH AMAZON BEDROCK KNOWLEDGE BASES AND FINE-GRAINED ACCESS CONTROL

When deploying an internal AI assistant using RAG (Retrieval-Augmented Generation) for an organization with multiple departments (Finance, Engineering, Executive...), a big challenge emerges: how do you let the AI answer accurately without leaking data across departments, given that each department holds sensitive documents like financial reports, system architecture docs, or M&A plans?

Key takeaways:

* Event-driven ingestion pipeline: documents are uploaded to Amazon S3 → an event fires through Amazon EventBridge → the message is pushed to Amazon SQS → AWS Lambda processes and attaches metadata → an EventBridge Schedule periodically triggers a Lambda ingest job that loads data into Amazon Bedrock Knowledge Bases, with embeddings stored in Amazon S3 Vectors.
* The entire ingestion pipeline is designed to be serverless and event-driven, which helps lower operational costs compared to maintaining fixed infrastructure.
* Query-side architecture: users go through Amazon CloudFront → are authenticated via Amazon Cognito → are protected by AWS WAF → requests hit Amazon API Gateway → a Lambda Authorizer checks access → Amazon Verified Permissions evaluates authorization policies → a Lambda middleware handles business logic → Amazon Bedrock Knowledge Bases performs the retrieval and returns results.
* The standout feature is Fine-Grained Access Control: combining Amazon Cognito, a Lambda Authorizer, and Amazon Verified Permissions to check not just "is the user logged in" but also "which department does the user belong to," "can they view this document," and "can they query this data."
* Core lesson: when building enterprise GenAI systems, the hardest part isn't the LLM or prompt engineering — it's data management, metadata, access control, and internal information security.

This is a valuable case study for organizations looking to deploy production-ready, multi-department RAG systems — especially the approach of pairing Amazon Bedrock Knowledge Bases with Amazon Verified Permissions to achieve both scalability and strong data security.

...Image...![alt text](/images/3-BlogsPosted/blog3_image.png)![alt text](/images/3-BlogsPosted/blog3_image-1.png)![alt text](/images/3-BlogsPosted/blog3_image-2.png)

Original article: https://aws.amazon.com/blogs/architecture/secure-multi-tenant-rag-with-amazon-bedrock-and-verified-permissions/