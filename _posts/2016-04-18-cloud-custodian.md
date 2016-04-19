---
layout: post
title: cloud custodian
---

Really quick post here before I head to bed. So today an internal project was open sourced, it's call [cloud-custodian](https://github.com/capitalone/cloud-custodian).

cloud-custodian allows you to manage your AWS resource is a effective manner via yaml config files.

Its actually pretty slick, and I've been using it internally at Capital One to make sure
we are well managed, not wasting resources, and following policies (eg: unencrypted S3 buckets)

For example, you want to ensure you have the proper tags on an EC2 instance or other wise kill said resources:

```
- name: tag-compliance
   resources: ec2
   description:
     Terminate resources which do not meet policy in 4 days
   filters:
     - State.Name: running
     - "tag:MyTagICareAbout": absent
   actions:
     - type: mark-for-op
       op: terminate
       days: 4
```

The EC2 instance will get tagged with a custodian tag (`c7n_status`) and be terminated
in 4 days. The custodian will typically be run on a regular interval to ensure
it is performing the proper tasks being requested from it.

@kapilt is the brains behind it, and has done an excellent job building this from
scratch. Hoping I can contribute something in the near future once I have some free time at work.

But I did get a [commit](https://github.com/capitalone/cloud-custodian/commit/92d676b027df00c9e21af65eca46e05519f8e107) in! HAHA :)

If you are using AWS and need something to help manage your resources, check it out: [https://github.com/capitalone/cloud-custodian](https://github.com/capitalone/cloud-custodian)
