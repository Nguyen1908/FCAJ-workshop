---
title: "Blogs Posted"
weight : 3
chapter : false
pre : " <b> 3. </b> "
---

### [Blog 1 - From Hourly Cache To Real-Time Pricing: How Samsung Solved Price Synchronization With AWS Lambda Response Streaming](3.1-Blog1/)
This blog covers how Samsung.com removed its hourly-refreshed intermediate cache layer — which caused permutation explosion and synchronization lag — and moved to a real-time pricing model that queries the Pricing Engine directly, powered by Amazon CloudFront combined with AWS Lambda Response Streaming. A great case study on prioritizing data accuracy over pure caching-based performance optimization.

### [Blog 2 - Building Multi-Department RAG With Amazon Bedrock Knowledge Bases And Fine-Grained Access Control](3.2-Blog2/)
This blog covers how to build an internal enterprise RAG system on Amazon Bedrock Knowledge Bases, allowing multiple departments (Finance, Engineering, Executive, etc.) to share a single Knowledge Base while still enforcing fine-grained, document-level access control through Amazon Cognito, a Lambda Authorizer, and Amazon Verified Permissions.

### [Blog 3 - Can Amazon Cognito Enable Login Without SMS OTP?](3.3-Blog3/)
This blog covers a solution combining Amazon Cognito CUSTOM_AUTH with Vonage's APIs (Identity Insights, Silent Authentication, Fraud Defender) to reduce OTP fraud and let users log in with almost no OTP entry required, based on real-time risk assessment.