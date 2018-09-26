# SRE-vocabulary
A vocabulary collection for SREs (mostly influenced by Google SREs)

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

Downtime per month is calculated at 30 days.<sup id="a2">[2](#f2)></sup>

### Error Budget

### Four Golden Signals

#### Saturation

#### Latency

#### Errors

#### Traffic

### Monitoring

#### Alerts

#### Tickets

#### Logs

### MTTR
Mean Time To Recover. MTTR is the average time that a device will take to recover from any failure.<sup id="a3">[3](#f3)</sup>

### MTBF
Mean Time Between Failures. MTBF is the predicted elapsed time between inherent failures of a mechanical or electronic system, during normal system operation. MTBF can be calculated as the arithmetic mean (average) time between failures of a system. The term is used for repairable systems, while mean time to failure (MTTF) denotes the expected time to failure for a non-repairable system.<sup id="a4">[4](#f4)</sup>

### MTTF
Mean Time To Failure. MTTF denotes the expected time to failure for a non-repairable system.<sup id="a4">[4](#f4)</sup>

### SLI
Service Level Identicator. A SLI is a carefully defined quantitative measure of some aspect of the level of service that is provided.<sup id="a5">[5](#f5)</sup>

### SLO
Service Level Objective. A SLO is a target value or range of values for a service level that is measured by an SLI.<sup id="a5">[5](#f5)</sup>

### SLA
Service Level Agreement. A SLA is a (legal) agreement with repercussions for failure to meet.<sup id="a5">[5](#f5)</sup>

## Sources
<b id="f1">1</b> Google SRE Interview, Niall Murphy and Ben Treynor, "What is 'Site Reliability Engineering', 2018-09-26, https://landing.google.com/sre/interview/ben-treynor.html [↩](#a1)  
<b id="f2">2</b> https://interworks.com/blog/rclapp/2010/05/06/what-does-availabilityuptime-mean-real-world/ [↩](#a2)  
<b id="f3">3</b> https://en.wikipedia.org/wiki/Mean_time_to_recovery [↩](#a3)  
<b id="f4">4</b> https://en.wikipedia.org/wiki/Mean_time_between_failures [↩](#a4)  
<b id="f5">5</b> Google Cloud Next 2018: Nori and Dan, "Best Practices from Google SRE", 2018-07-26, https://www.youtube.com/watch?v=XPtoEjqJexs [↩](#a5)  
