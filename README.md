# AWS Learner 2021 <!-- omit in toc -->

Table of Contents
- [Architecting for Reliability on AWS](#architecting-for-reliability-on-aws)
	- [Architecting for Availability](#architecting-for-availability)

## Architecting for Reliability on AWS

<br>

### Architecting for Availability

<br>

**Defining Reliability, Resiliency and Availability**

*Reliability or resiliency*
> The ability of an application to avoid and recover from failure

*Availability*
> The percentage of time that an application is performing as expected\
> Poor performance implies low availability\
> Uptime isn't the same as availability

*Decide how much availability you need before designing your AWS environment*

Availability and Annual Downtime
| 99.0%           |       99.9%        |    99.99%    |   99.999% |
| :-------------: | :----------------: | :----------: | :-------: |
| 3 days 15 hours | 5 hours 45 minutes | About 1 hour | 5 minutes |

<br>

**Architecting for 99.9% Availability**

*Traditional Application*
> Runs on Windows or Linux\
> You can "life and shift" it to AWS without changing its code\
> ⁃ Example: SQL-backed web application\
> How you design for availability depends on the architecture of the application

*Web-based Video Processing Application*
> Front end\
> ⁃ Web interface\
> ⁃ Video processing logic\
> Back end\
> ⁃ SQL database

![AWS Architecture](img/AWS_Architecture.png)

*Calculating Availability - EC2*
> The service level agreement (SLA) for each service includes its annual availability\
> Availability of an EC2 instance is 90%\
> Failure rate of each instance is 10%

<br>

**Loose Coupling**

*Loose vs. Tight Coupling*
| Loose coupling                                         |                                      Tight Coupling |
| ----------------------------------------------------: | :------------------------------------------------- |
| One component *doesn't* depend on a specific component | One component *does* depend on a specific component |
| URL points to ELB                                      |                      URLpoints directly to instance |
| One-to-many relationship                               |                             One-to-one relationship |

*What About EFS?*
> Elastic services are always composed of redundant components\
> Elastic services are always loosly coupled with other resources

*Redundancy and Loose Coupling*
> Redundancy ➔ loose coupling ➔ availability

*Loose Coupling and Performance*
> Independently scale resources without impacting availability\
> Performance and availability are linked\
> ⁃ Poor performance leads to low availability\
> ⁃ Good performance helps maintain availability
