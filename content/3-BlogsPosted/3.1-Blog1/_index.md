---
title: "Blog 1"
date: 2026-06-16
weight : 1
chapter : false
pre : " <b> 3.1 </b> "
---

# FROM HOURLY CACHE TO REAL-TIME PRICING: HOW SAMSUNG SOLVED PRICE SYNCHRONIZATION WITH AWS LAMBDA RESPONSE STREAMING

In e-commerce, product pricing is one of the most sensitive pieces of data — if the price shown on a product page differs from the price at checkout, customer trust takes a real hit. Samsung.com, Samsung's direct-to-consumer sales channel, recently overhauled how it serves pricing data using AWS Lambda Response Streaming combined with Amazon CloudFront.

Key takeaways:

* The old architecture relied on a Data Aggregation layer with an hourly Cron Job that pre-computed every possible price combination (color, storage, promotions, regional offers...) and stored the results in cache.
* The "Permutation Explosion" problem: with 30+ SKUs multiplied by many variants, the number of combinations to pre-compute grows exponentially, wasting compute and storage on data that may never be accessed.
* The "Synchronization Lag" problem: since the Cron Job only ran once an hour, cached prices could lag up to 60 minutes behind reality — a flash sale starting at 10:05 AM would still show the old price until the next run at 11:00 AM.
* The new approach: eliminate the Data Aggregation layer entirely and always fetch pricing directly from the Pricing Engine (the source of truth) at the moment a user makes a request.
* New flow: CloudFront checks its edge cache → on a cache miss, it invokes Lambda → Lambda fans out multiple parallel requests to the Pricing Engine → results stream back to the user as soon as they're ready → CloudFront caches the response for a short period to keep performance high.
* Lambda Response Streaming reduces Time To First Byte (TTFB) because data is sent back as soon as it's available, instead of waiting for the entire response to be assembled first.
* Core AWS services involved: Amazon CloudFront, AWS Lambda, Lambda Response Streaming, Lambda Function URLs, and Provisioned Concurrency.

The biggest lesson here isn't really about Lambda Response Streaming as a technology — it's about architectural thinking. Caching is usually treated as the go-to fix for performance problems, but in systems where data accuracy (like pricing) matters more than raw speed, caching itself can become the source of business-critical bugs. Sometimes a simpler architecture that stays close to the source of truth outperforms a system with many layers of intermediate caching.

...Image...![alt text](/images/3-BlogsPosted/blog1_image.png)![alt text](/images/3-BlogsPosted/blog1_image-1.png)

Original article: https://aws.amazon.com/blogs/architecture/how-samsung-achieved-real-time-pricing-with-aws-lambda-response-streaming/