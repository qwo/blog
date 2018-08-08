+++
title ="How well do you know your Cloud?"
description = "Comparing and Contrasting GCP Certifications"
date = 2018-07-28T10:01:57-05:00
tags = ["GCP", "Certifications"]
+++


Back in May, I [shared on Linkedin](https://www.linkedin.com/feed/update/urn:li:activity:6399229464563187713/) that I received my [Google Cloud Architect](https://cloud.google.com/certification/cloud-architect) certification. It was probably my most shared post ever on the platform. A week later, I attained the [Data Engineer](https://cloud.google.com/certification/data-engineer) certification and at the beginning of July, the [Associate Cloud Engineer](https://cloud.google.com/certification/cloud-engineer). I ventured to guess that I was the first engineer at Cloudreach to get all three. I get a few common questions and I hoped to answer all here:

- What's the big difference between them all?
- How do you recommend preparing for them?
- What's the point of professional certifications?

--- 
> A fun aside is that all the certifications for GCP and other companies are hosted on [credential.net](https://www.credential.net/), a blockchain backed cert platform. 


### All of my certifications can be verified respectively below:

- [Cloud Architect](https://www.credential.net/eaf9xkih?key=0c7d614393291892e18cef85000144013e32013d77978c9c71f4581f11314342)
- [Data Engineer](https://www.credential.net/4k6bclwz?key=81f4043570401173ae2a588da3f425647812eb4c5b8fbb249ce31cf3ce5e7914)
- [Associate Engineer](https://www.credential.net/2gj7nquy?key=0984470f346baaca2ec058bd19d1eb504fd4afcb7c68661328ddc1c3bb7f932b)

----
## Background
For my first job, I worked at [an Advertising Agency](https://thisisgrow.com/) that hosted most of their applications and infrastructure on Google Cloud Platform. For two years, I worked mostly with App Engine, Cloud Storage, and Compute Engine to build ad infrastructure. Prior to that, I had only used Google APIs and generated service keys to use for Apps.

Google was early in the space with releasing App Engine in 2008. The service became Generally Avaliable(GA) in November 2011. They released Google Compute Engine, a competitor to Amazon Elastic Compute Cloud (EC2) near the end of 2013. Google was slow in maturity for convincing enterprise companies to adopt Google Cloud Platform as a serious contender to Amazon.

---
## Why?

AWS has a huge incumbent stake in the market with AWS being an [over 250 billion dollar business](https://seekingalpha.com/article/4140036-much-amazon-web-services-worth-now)
Having worked on both platforms, I have a strong belief that the Google Cloud Platform will be able to outgrow its competitors based on the features and services the platform offers.

However, in a market, not even the best-designed tools built by Google can win unless they capture commercial market share. And the only way to do that is to establish their own ecosystems and teach developers how to use their platform.

--- 

# Comparing the 3 Exams

## Overview
Largely the exams aim to be a practical baseline assessment of day-to-day duties at a Google Cloud Platform oriented company. I found the exams practical and fair in their assessments of candidates comprehension compared to Amazon. (I have done the Solutions Architect Associate, Professional, and the Associate Developer Certifications for AWS).

These summaries are also in the outlines and course guides but I would summarize in their respective guides. IE the one for the [associate engineer outlines at a high level](https://cloud.google.com/certification/guides/cloud-engineer/) the topics and competencies you should be required to know.

## Assessment

### Cloud Architect

Goal: Test someone architecting solutions on Google Cloud Platform from either migration or greenfield development.

- Focus on Compute Engine
- Focus on Networking concepts
- Focused on case studies and migrations for right-sizing workloads

### Data Engineer

Goal: Assessing tradeoffs revolving around processing, analyzing, and storing data on Google Cloud Platform.

- Focus on using Dataflow vs Dataproc
- Focus on different data retention strategies and trade-offs
- Focus on Big data processing workflows
- Focus on the underlying the cases to use BigTable and BigQuery and their trade-offs
- Some case studies for choosing data sources

### Associate Engineer
Goal: Day-to-Day knowledge working at a company building and deploying applications on GCP.

- Focus on App Engine
- Focus on Kubernetes
- Focus on Gcloud Console
- No Case Studies

---
## What is the Associate Engineer?

As the newest exam it has the least information and most misconceptions out about it that I wanted to call out.     How is the associate cloud engineer different from professional cloud architect? 

```
> Apples : Oranges 
> AWS Solution Architect Associate : AWS Developer Associate  
> GCP Cloud Architect : GCP Associate Engineer 
```

I think they are very different; The Associate Engineer is poorly named; 
It's not like AWS SA Associate to - SA Associate Professional in AWS parlance. (A logical progression of step 1 to step 2)

GCP Associate Engineer is akin to the AWS Developer Associate certificate. 

The assessment covers "how would a day-to-day engineer focused on app development run workloads on cloud and use the tools in their tool bots. For Google Cloud this means lots of Google Container Engine/Kubenetes, Google App Engine, Storage, Instance template/managed group questions.

I think it by far a more "hands" on approach. Architect exam there were case studies and "migration" situations, whereas the Engineer exam did not have any. Compared to Data Engineer no really heavy questions on BigQuery or Big Table optimization or storage constraints; just knowing what these services are at a high level (relation/not relational/managed/not managed) was good enough (edited)
I had 21 questions I was sure about, 16 I was 80%> sure and 13 that were about 50/50 educated guesses. I ended up finishing in 70 minutes and reviewed the rest of my questions


---- 

## My Timetable to completion

I did these in an expedited fashion for my work but also having deep prior experience, I did it at an accelerated pace. Google does not reveal scores, so the pass threshold is unclear, unlike AWS where 60% correct is usually a pass on their averaged exams. 

For my first exam, I did the Cloud Architect for preparing for one weekend of 30 hours of review and study. I took it the following Monday and was able to earn a pass. (2 May 2018)

My second exam, I did the Data Engineering, by studying that following weekend with the same below resources, equally putting 30 hours of review and study. I was able to take it the following week again and earned a pass (8 May 2018).

Later on, to compete on a contest at work for a trip to GCP next, I decided to do the newer beta engineer exam with a weekend of prep but I likely spend only ~8 hours in preparation. I had to spend prior to this 3 months working knee-deep working in GCP actively again which made it easy. (6 July 2018)


## Preparation
- [GCP: Complete Google Data Engineer and Cloud Architect Guide](https://www.udemy.com/gcp-data-engineer-and-cloud-architect/) - Udemy Course. Most comprehensive set of courses for all 3 overview.
- [Cloud Academy Courses](https://cloudacademy.com/library/google/) - These were very comprehensive and I felt more intermediate-expert courses that gave you really useful information for the exam but also for day to day. 
- Case Studies Partner Portal - Google runs a partner portal for GCP, that people can sign up for. There are lots of great discussion and resources on the site.
- [Solutions Slides](https://docs.google.com/presentation/d/1vjm5YdmOH5LrubFhHf1vlqW2O9Z2UqdWA8biN3e8K5U/edit#slide=id.p99) -  familiarizing with icons and common architecture patterns. This is great for building diagrams also 
- Storage Options - Review heavily the storage options, costs between Storage, Datastore, BigQuery BigTable, CloudSQL, Persistent disk/SSD and the different time and latency tradeoffs. 
- Practice Quizzes for each exam - on their respective site there's a google form that gives you a good assessment to judge your familiarity after your first round of studying.
- [GCP Solutions](http://gcp.solutions/) - site with common GCP architect patterns flashcard style.


----

## Final Thoughts

The exams were great but do not beat real-world experience with the platform. I felt like I was in high school again studying for the SATs and general good test taking and studying practices were key. These exams are a great starting point for your journey to the Cloud. If you'd like to learn more, feel free to drop me a line on any of my social media or email channels.