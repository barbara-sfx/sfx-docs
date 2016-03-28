

 **Links may not work**

# Introduction

SignalFx is all about metrics - collecting, storing, visualizing, analyzing and alerting on them. If you're wondering why you should care, or just want to get a better feel for what they are - read on!

**Original has a TOC to the headings in the document here, which I haven't recreated**

# What is a metric?

A metric is anything that is _measurable_ (you can assign a numerical value to it) and _variable_ (changes over time).

For example, the current temperature or the price of a stock are examples of measurable things, as their numerical value changes over time. Things that have non-numerical values, such as a person's name, are not metrics because they cannot be measured. Likewise, numerical constants such as _pi_ (3.1415….) or the speed of light are always the same, so they are not metrics either.

# Common examples of metrics

Many things can be represented as metrics. For the purposes of monitoring, we loosely categorize them as infrastructure, application or business metrics.

## Infrastructure metrics examples:

* CPU% of a server
* number of bytes of free disk space
* number of bytes transmitted on a network interface

## Application metrics examples:

* Response time in milliseconds of an API call
* Cache hit ratio of an internal cache used in a service
* % of time spent on garbage collection by a JVM instance

## Business metrics examples:

* number of unique users who logged in over the last day
* number of new customers who signed up in the last hour
* Week over week percentage growth in revenue

# Metrics and logs

Logs are lists of actions or events that have occurred, and are commonly used by developers and operations teams for troubleshooting because of the ease with which detailed log data can be generated, and because it is often human-readable. In many cases, metrics are implicitly written into logs as part of an accounting of events.

For example, you might have a log containing the stack trace every time an exception occurs in a Java application. If you extract the text that represents the occurrence of an exception, tally up the number of times you see it in the log and correlate that with timestamps correctly, then effectively you have recreated a metric representing the number of exceptions.

In this sense, the log file can be thought of as a temporary container for the metric data, trading off detail and human readability (it's just text, after all) against efficiency of transport and ease of subsequent mathematical manipulation (as you would expect for numbers).

# Why are metrics useful?

By their very nature, metrics lend themselves to visualization, analytics and alerting.

## Visualization

The human brain is particularly good at visual pattern analysis. A page full of time/value pairs may feel like a jumble, but if you plot them on a chart, you will instantly make sense of the data. Trends and outliers become apparent right away, as does proportionality.

## Analytics

Calculating aggregations (e.g. percentiles over a large population), discovering trends (e.g. percentage rise in daily revenue compared to a month ago) and finding correlations (e.g. between growth in API calls and number of logged-in users on a website) are all examples of analytics for which metrics are well-suited.

## Alerting

It is trivial to compare a metric against a threshold value and send out a notification when it crosses the threshold.

# How are metrics used by developers or operations teams?

Monitoring, scaling and optimization are three key use cases enabled by metrics. For any business with software competencies - and that is most companies, today - satisfying these use cases is also critical to the success of the business.

## Monitoring

In its simplest form, monitoring uses the visualization and alerting capabilities of metrics to let you manage individual instances or components, such as the CPU utilization % of a specific server. In an environment with greater complexity, monitoring is no longer just a visualization and alerting problem, but is now also an analytics problem. For example, in a service with tens or hundreds of nodes, it is inefficient and noisy to monitor the health of individual nodes, each of which can generate their own alerts.  It is far better to monitor the overall health of the service by calculating a single metric of overall service performance, and receiving a single alert when the service is performing below expected service levels.

## Scaling

How much headroom does a node have? How much capacity should be added across the multiple tiers of a distributed application architecture - running on cloud infrastructure, of course - in order to support X more users of a service? While it's possible to build static models to plan for such changes, the reality is that the characteristics of the application components are changing constantly. As a result, static models become obsolete rapidly, and models that capture the dynamic nature of performance - in other words, metrics - are really the only way to accurately anticipate scaling requirements.

## Optimization

Performance and cost optimization are among the top two or three focus areas of most engineering organizations. Comparison of performance metrics with their historical values helps measure the effectiveness of optimizations or identify performance regressions introduced by new code. With any reasonably complex system, instrumenting each component or service to capture important performance characteristics (e.g. latency of each stage) helps identify the longest poles and the best targets for engineering effort. Similarly, mapping out how costs will increase with scale can help identify and address top cost centers within a service.

## Serving business needs

For any business with a software competency, all of the above reasons to use metrics apply not just to the developer community and the operations teams, but also to their business counterparts. 24/7 expectations on the part of customers mean that monitoring has to be up to snuff. Scale tends to correlate with revenue and user growth in most software businesses. Performance is not just a matter of engineering prioritization, but also critical to customer satisfaction and retention.

# When should I use metrics? When should I use logs?

While logs and metrics can be used in similar ways, they tend to have complementary strengths, leading many practitioners to use both.

!https://support.signalfx.com/hc/en-us/article_attachments/201806159/table1.png!

In fact, while SignalFx primarily handles metrics, it also supports [event](https://support.signalfx.com/hc/en-us/articles/203758549#event) data natively in SignalFx.
