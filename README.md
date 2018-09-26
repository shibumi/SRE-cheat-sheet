# SRE-cheat-sheet
A cheatsheet for SREs (mostly influenced by Google SREs). It is meant as a landing page to quickly look up a certain keyword. If you want to go more into the details, I suggest you read the Google SRE book. It is for free: https://landing.google.com/sre/book/

## Dictionary
### Site Reliability Engineering
"Fundamentally, it’s what happens when you ask a software engineer to
design an operations function" -- Ben Treynor, VP of Engineering @ Google.<sup id="a1">[1](#f1)</sup>

### Uptime
| Availability % | Downtime per year | Downtime per month | Downtime per Week |
|----------------|-------------------|--------------------|-------------------|
| 90%            | 36.5 days         | 72 hours           | 16.8 hours        |
| 95%            | 18.25 days        | 36 hours           | 8.4 hours         |
| 98%            | 7.30 days         | 14.4 hours         | 3.36 hours        |
| 99%            | 3.65 days         | 7.20 hours         | 1.68 hours        |
| 99.5%          | 1.83 days         | 3.60 hours         | 50.4 minutes      |
| 99.8%          | 17.52 hours       | 86.23 minutes      | 20.16 minutes     |
| 99.9%          | 8.76 hours        | 43.2 minutes       | 10.1 minutes      |
| 99.95%         | 4.38 hours        | 21.56 minutes      | 5.04 minutes      |
| 99.99%         | 52.6 minutes      | 4.32 minutes       | 1.01 minutes      |
| 99.999%        | 5.26 minutes      | 25.9 seconds       | 6.05 seconds      |
| 99.9999%       | 31.5 seconds      | 2.59 seconds       | 0.605 seconds     |

Downtime per month is calculated at 30 days.<sup id="a2">[2](#f2)</sup>

### Error Budget
Error budget is generall the budget you can spend on pushing features. Let's say you have an uptime of 90% for your application or service. This means that you can have a downtime of 36.5 days per year, this is a downtime of 72 hours per month. You can either spend this downtime on fixing errors or you build your system reliable and spend it on pushing new features. It's fully up to you. You should just make sure that you freeze new features until your error budget has recovered. This has several advantages:

1. Your Software Engineers will try to build your application as much as stable. Because if your application is unstable they will need their error budget for fixing these errors instead of pushing new features.
2. If you have a stable application you are free to push new features as much as your error budget allows you to.
3. Your uptime will be consistent to your SLA. Nobody wants to get sued, trust me.

### Dickerson's Hierarchy of Service Reliability

### Four Golden Signals
A group of basic questions about your service regarding monitoring.<sup id="a5">[5](#f5)</sup>  
<img src="https://github.com/shibumi/SRE-vocabulary/raw/master/figures/four_golden_signals.png" width="352" height="307" />

#### Saturation
This definition is up to you. It can be the capacity of the service like the CPU utilization. Ask yourself at what point your service could fall over and try to measure the metric for that point.

#### Latency
Users expect blazing fast apps these days. So you want to definitly monitor your latency.
At Google they measure latency in three numbers:

* P50: The 50th percentile or the median latency.
* P90: The 90th percentile.
* P99: The 99th percentile.

Do not see latency as an average.<sup id="a5">[5](#f5)</sup>

#### Errors
Indicator for failures while serving your traffic. Usually measured in EPS (Errors Per Second).

#### Traffic
Normally measured in RPS (Requests Per Second) or QPS (Query Per Second).

### Valid Monitoring Output
#### Alerts
An alert is something where a human needs to take action immediately to prevent a system crash or a degeneration of your service.

#### Tickets
Tickets are everything, where a human needs to take action but not now. Usually you should have enough time to fix this issue, in any other case it's an alert.

#### Logs
This metrics are only for diagnostic, forensic purposes and post mortems.

### Defense In Depth
Failures will always happen. Get used to it. There is nothing you can do about it, but what you can do is tolerate them and have them automatically get fixed. If you design your system, that it is tolerating point failures you will have already one problem less.<sup id="a1">[1](#f1)</sup>

### Graceful Degredation
"Graceful degradation is the ability to tolerate failures without having complete collapse. For example, if a user's network is running slowly, the Hangout video system will reduce the video resolution and preserve the audio. For Gmail, a slow network might mean that big attachments won't load, but users can still read their email. All these are automated responses that give you high availability without a human having to do anything."<sup id="a1">[1](#f1)</sup>

### Wheel Of Misfortune
The "Wheel Of Misfortune" is a role-game, where a previous postmortem is reenacted with a cast of engineers playing roles as laid out in the postmortem.<sup id="a6">[6](#f6)</sup>

### Mean Time To Recover (MTTR)
MTTR is the average time that a device will take to recover from any failure.<sup id="a3">[3](#f3)</sup>

### Mean Time Between Failures (MTBF)
MTBF is the predicted elapsed time between inherent failures of a mechanical or electronic system, during normal system operation. MTBF can be calculated as the arithmetic mean (average) time between failures of a system. The term is used for repairable systems, while mean time to failure (MTTF) denotes the expected time to failure for a non-repairable system.<sup id="a4">[4](#f4)</sup>

### Mean Time To Failure (MTTF)
MTTF denotes the expected time to failure for a non-repairable system.<sup id="a4">[4](#f4)</sup>

### Service Level Indicator (SLI)
SLI is a carefully defined quantitative measure of some aspect of the level of service that is provided.<sup id="a5">[5](#f5)</sup>

### Service Level Objective (SLO)
SLO is a target value or range of values for a service level that is measured by an SLI.<sup id="a5">[5](#f5)</sup>

### Service Level Agreement (SLA)
SLA is a (legal) agreement with repercussions for failure to meet.<sup id="a5">[5](#f5)</sup>

### Capability Maturity Model (CMM)

### Postmortem

## Sources
<b id="f1">1</b> Google SRE Interview, Niall Murphy and Ben Treynor, "What is 'Site Reliability Engineering', 2018-09-26, https://landing.google.com/sre/interview/ben-treynor.html [↩](#a1)  
<b id="f2">2</b> https://interworks.com/blog/rclapp/2010/05/06/what-does-availabilityuptime-mean-real-world/ [↩](#a2)  
<b id="f3">3</b> https://en.wikipedia.org/wiki/Mean_time_to_recovery [↩](#a3)  
<b id="f4">4</b> https://en.wikipedia.org/wiki/Mean_time_between_failures [↩](#a4)  
<b id="f5">5</b> Google Cloud Next 2018: Nori and Dan, "Best Practices from Google SRE", 2018-07-26, https://www.youtube.com/watch?v=XPtoEjqJexs [↩](#a5)  
<b id="f6">6</b> "Postmortem Culture: Learning from Failure", John Lunney and Sue Lueder, 2018-09-26, https://landing.google.com/sre/book/chapters/postmortem-culture.html [↩](#a6)  

## Additional Links
A more technical cheatsheet: https://github.com/michael-kehoe/awesome-sre-cheatsheets  
DevOps: "Where do I start? Cheatsheet" by Microsoft: https://blogs.technet.microsoft.com/juliens/2016/02/14/devops-where-do-i-start-cheat-sheet/  
"So you want to be an SRE" by hackernoon.com: https://hackernoon.com/so-you-want-to-be-an-sre-34e832357a8c  
The Google SRE Landing page: https://google.com/sre
