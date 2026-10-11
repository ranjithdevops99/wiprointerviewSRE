🎤 INTRODUCTION (FINAL VERSION)

“Hi, I’m Ranjith.

Hi, this is Ranjith. I have around 10 years of experience in Cloud, DevOps, and Site Reliability Engineering, with a strong focus on AWS and Azure infrastructure, Kubernetes, observability, automation, and production support.

In my recent role at **Speedy Hire**, I worked as part of a centralised SRE team supporting applications and microservices across different environments. The applications were primarily running on Azure AKS, with supporting applications and infrastructure across Azure and AWS.My main responsibilities included monitoring application availability and performance, handling production incidents, supporting deployments and rollbacks, and working on root cause analysis and preventive actions. I used Prometheus, Grafana, Azure Monitor, and Application Insights to monitor latency, error rates, traffic, resource saturation, pod health, and overall application performance. I also worked on dashboards and alerting improvements to enhance visibility and support faster incident detection.
On the DevOps side, I worked with Azure DevOps, Docker, Helm, and Terraform, along with Shell scripting to automate repetitive operational activities. I also worked closely with development and platform teams to improve observability, reduce alert noise, and strengthen platform reliability.
**Previously, at Lloyds Bank through Wipro, I worked as a DevSecOps and AEM Technical Lead**, supporting multiple applications and websites across cloud environments. My responsibilities included AWS infrastructure and operations, CI/CD pipeline management using Jenkins and Azure DevOps, containerisation with Docker, and Kubernetes-related technologies including EKS, AKS, and Rancher.
I was also involved in cloud security and vulnerability management, working with tools and controls such as Fortify, Twistlock, WAF, and access management. My work included supporting production issues, improving deployment processes, troubleshooting infrastructure problems, and collaborating with application, security, and infrastructure teams to maintain stable and secure environments.Across both roles, I have gained strong experience in production incident management, monitoring and alerting, cloud infrastructure, deployment automation, security, and operational improvement.


DAY-TO-DAY ACTIVITIES 🎤 Answer (Use this directly):

In my day-to-day role, I mainly work on AWS infrastructure and support Linux-based production environments.

“In my day-to-day role, my main focus is SRE, production reliability, DevOps and automation.I start by monitoring application and infrastructure health using Application Insights, Azure Monitor, Prometheus and Grafana. I look at availability, latency, error rates, traffic, CPU and memory, and review alerts and dashboards to make sure the services are stable.I also work on the DevOps side, supporting Azure CI/CD pipelines for Java-based application deployments, validation, rollback activities and deployment automation. I work with Docker, Helm and Kubernetes as part of the application deployment process.From the infrastructure side, I work across both AWS and Azure environments. I use Terraform for infrastructure as code to provision and manage cloud resources, and I support the underlying Linux and containerised environments. Depending on the application, this can involve services such as EC2, load balancing and networking in AWS, or AKS and other Azure services.When production incidents occur, I analyse logs, metrics and traces, identify the affected layer and coordinate with the relevant teams to restore the service quickly and safely.I also use Bash and Python scripting to automate repetitive operational tasks, reduce manual effort and improve efficiency. Overall, my focus is on maintaining high availability, supporting reliable deployments, monitoring system performance, resolving production issues and continuously improving automation and system reliability.”

K8s regular issues

CrashLoopBackOff
OOMKilled - pod was terminated because it exceeded memory limits.” set up resourecqota and limit -even we got error then collect Thread dump and heap memory from particular pod

Liveness/Readiness Fail - liveness is for to check pod healty or not ,Readiness is to check ready to recieve trafic or not

ImagePullBackOff
Pod Pending ,Node Not Ready ,503 Errors ,Ingress Issues ,HPA Issues ,PV Issues Resource quota -for namespace will use resource quota Resource limit - for Pod level we implemenr tesource limit

🚨 IMPORTANT ALERTS

✅ Pod restart ✅ High CPU ✅ High memory ✅ Pod not ready ✅ 5xx errors ✅ Node down
PHASE 1 — PRODUCTION APPLICATION SUPPORT

**a production microservice suddenly experiences high latency and HTTP 5xx errors. Customers are reporting timeout**s
“In my SRE role at Speedy Hire, I supported production applications and microservices where availability and performance were critical. In this scenario, the application suddenly experiences increased response times and HTTP 5xx errors, affecting customers.”

“My responsibility is to identify the root cause, minimise customer impact, restore service safely and implement preventive actions.”
“First, I would use Dynatrace to assess the impact and identify where the problem is occurring.
I would open the service overview and check response time, failure rate, throughput and the affected services. I would also look at the problem analysis to understand when the issue started and whether it correlates with a deployment or infrastructure change.
Next, I would use distributed tracing, including PurePath, to follow individual requests across the microservices. This would help me identify whether the delay originates in the application, a database call or another downstream dependency.
I would then correlate the traces with application logs and infrastructure metrics. If the application runs on Kubernetes, I would check pod health, CPU and memory utilisation, container restarts, readiness probes and resource limits.
For example, suppose Dynatrace shows that response times increased immediately after a deployment, and distributed traces identify a slow downstream service. I would investigate the dependency and recent changes, coordinate with the application team, and assess whether rolling back the release or applying another safe mitigation is appropriate.Throughout the incident, I would communicate updates to stakeholders. After applying the mitigation, I would use Dynatrace to verify that response times and failure rates have returned to acceptable levels.Finally, I would conduct a root cause analysis, review why the existing alerts did not prevent or detect the issue earlier, and improve dashboards, alert thresholds and preventive controls.”

R — Result
“The objective is to restore service, minimise customer impact and prevent recurrence. Dynatrace helps connect service-level symptoms with distributed traces and infrastructure metrics, allowing the team to identify the bottleneck faster and make evidence-based decisions.”

“What metrics do you normally monitor in Speedy?”“The key metrics I monitored across the applications at Speedy Hire were availability, latency, traffic, error rates, CPU and memory utilisation, and Kubernetes pod health.As we supported multiple applications and microservices, we used different monitoring and observability tools depending on the project. Prometheus and Grafana were used for infrastructure metrics, dashboards and alerting, while Azure Monitor and Application Insights provided Azure infrastructure and application-level monitoring.For some projects, we implemented Dynatrace to improve end-to-end application observability, monitor service performance, analyse distributed traces and identify bottlenecks across microservices and their dependencies.
We also used SLI, SLO and KPI concepts to assess service reliability, monitor performance against expectations and support proactive incident management.”


Scenario 2: SLI, SLO, SLA and Error Budget 
Interviewer:  how do you measure application reliability, and what would you do if a service started breaching its SLO?”

### S — Situation
“At Speedy Hire, we supported multiple applications and microservices where maintaining availability and performance was important. We monitored application health using Prometheus, Grafana, Azure Monitor, Application Insights and Dynatrace on selected projects.”
### T — Task
“My responsibility was to monitor service performance, identify reliability issues early, and work with engineering teams to maintain stable production environments.”
### A — Action
“I would start by identifying the key SLIs, such as availability, request success rate and latency. Based on business requirements, we would define SLOs, for example, a target of 99.9% availability over 30 days.I would monitor these indicators through dashboards and alerts. If a service started breaching its SLO, I would investigate the error rates, response times, infrastructure metrics and recent deployments to identify the cause.I would also assess the error budget. If it was being consumed too quickly, I would highlight the reliability risk and recommend prioritising stability improvements before taking additional release risks.An SLA is different from an SLO because it represents a formal commitment to the customer. I would ensure the agreed service commitments were monitored and any potential breach was communicated through the appropriate process.
After resolving the issue, I would review the incident, identify monitoring gaps and track preventive actions.”
### R — Result
“This approach helps teams measure reliability objectively, make informed release decisions and balance delivery speed with production stability.”

Scenario 3: Dynatrace — identifying application performance bottlenecks
Interviewer: “Ranjith, suppose an application is running, but response times have increased significantly. How would you use Dynatrace to identify the root cause?

### S — Situation
“At Speedy Hire, we supported multiple applications and microservices, so maintaining performance and identifying bottlenecks across service dependencies was important for production stability.”
### T — Task
“My responsibility would be to investigate the performance degradation, identify the affected component, minimise customer impact and restore normal application performance.”
### A — Action
“I would start by checking Dynatrace to identify which services are experiencing increased response times or failure rates. I would review the service overview and problem analysis to understand when the issue started and which components are affected.Next, I would use distributed tracing and PurePath to follow individual requests across the application and identify slow transactions, database calls or downstream dependencies.I would correlate the findings with application logs, infrastructure metrics and recent deployments. If the application runs on Kubernetes, I would also check pod health, CPU and memory utilisation, restarts and resource limits.For example, if a distributed trace showed that most of the response time was spent waiting for a database call, I would work with the database and application teams to investigate query performance, connection usage and recent changes.After applying the appropriate fix, I would verify that response times and error rates had returned to acceptable levels. I would then review the incident and improve alerts or dashboards to detect similar issues earlier.”
### R — Result
“This approach helps isolate performance bottlenecks, reduce troubleshooting time and improve application reliability through evidence-based investigation and preventive actions.”

**Scenario 4**Production Application Is Down**
“If a production application goes down, I would treat it as a high-priority incident and first understand the impact through our monitoring. I would check the application health, error rates, availability and infrastructure metrics to identify where the problem is happening. In Speedy, depending on the application, this could be an Azure AKS workload or an application running on AWS infrastructure. I would then check the application logs and look for any recent deployment, configuration or infrastructure changes. I would also check whether any dependent service is causing the failure.Once I identify the likely cause, I would take the appropriate recovery action, such as rolling back a recent change, recovering the affected service or working with the relevant team to resolve a dependency issue.During the incident, I would keep the stakeholders updated and focus on restoring the service safely. Once it is recovered, I would verify the application is stable through monitoring and then work on the RCA and preventive actions.”

**Scenario 5 — Application Pod Keeps Restarting “One of your production application pods is continuously restarting. How would you handle it?”**
“I would start by checking the monitoring to understand when the restarts began and whether it is isolated to one pod or affecting the wider application. From there, I would look at the pod health, application logs and Kubernetes events to understand what is actually causing the restart. I would particularly look for application errors, memory or CPU issues, failed health checks and configuration problems.At the same time, I would check if there was a recent deployment or configuration change that could be related to the issue. If a recent change is confirmed as the cause, I would follow the approved rollback process to restore the previous stable version.Once the root cause is identified, I would apply the appropriate fix and keep monitoring the application to make sure the pods remain stable.Finally, I would document the RCA and work on preventive actions, such as improving resource settings, health checks, monitoring or deployment validation.”

**“A production Linux server suddenly has very high CPU usage. How would you handle it?”**
“I’d start by checking the monitoring to understand how high the CPU has gone, when it started and whether there is any impact on the application. For example, if I see CPU has increased from around 50% to 95%, I’d identify which process is consuming the CPU and check whether it is the Java application or another system process.If it is the Java process, I’d correlate that with application traffic, logs and any recent deployment or configuration change. If traffic has also increased significantly, it could be a genuine capacity issue rather than an application problem. Based on what I find, I’d take the appropriate action. For example, if it is increased traffic, I’d scale the application or use available capacity. If it is related to a recent application change, I’d work with the development team and follow the approved rollback process if necessary. Once the CPU returns to a normal level, I’d monitor the application and server to make sure performance remains stable. Finally, I’d capture the RCA and look at preventive actions such as capacity planning, application optimisation or better alerting.”Scenario 4 — High CPU in Production “You receive an alert that CPU usage is very high on a production application. How would you handle it?”

**A Deployment Causes a Production Problem“A new application version has been deployed to production and users are reporting errors.**
“I would immediately compare the timing of the errors with the deployment to see whether there is a clear connection.If the issue started immediately after the release, I would check the application health, error rate and user impact and compare the new version with the previous stable version.If the new release is confirmed as the likely cause, my priority would be to restore the stable service rather than spending too much time debugging while customers are affected. I would follow the approved rollback process and closely monitor the recovery.Once the application is stable, I would work with the development team to understand what went wrong and why the issue was not identified before production.We would then improve the deployment process, testing or monitoring so that a similar issue can be detected earlier in the future.”

**Scenario 8 — Monitoring & Observability“How did you monitor your applications in the Speedy project?”**
“In Speedy, monitoring was a major part of my SRE responsibilities. We used Prometheus and Grafana for application and infrastructure metrics, along with Azure Monitor and Application Insights for Azure and application-level monitoring.I mainly focused on metrics such as availability, latency, traffic, error rates, CPU and memory. Application Insights was also useful for understanding application behaviour and dependencies. We used these metrics to build dashboards, identify abnormal behaviour and support incident investigation. We also used SLI and SLO concepts to understand whether the applications were meeting their reliability targets.My focus was not just reacting to alerts, but using monitoring proactively to identify performance or reliability issues before they became larger production problems.”

**Scenario 9 — SLI, SLO and KPI in SpeedyCan you explain your SLI, SLO and KPI experience in the Speedy project?”**
“In Speedy, we used SLI, SLO and KPI to measure the reliability and performance of our applications.SLI was the actual measurement we monitored, such as availability, latency or error rate.SLO was the target we wanted the application to achieve based on those measurements.KPI helped us track the overall performance and operational health of the service. From an SRE perspective, I used these measurements to monitor whether the applications were meeting their reliability expectations. If we saw an SLO moving towards a breach, we could investigate the reason and take action before it became a bigger production issue. So, for me, SLI tells us what is happening, SLO tells us what level we expect, and KPI helps us track overall performance and health.”

**Scenario 10 — Deployment & Rollback in Speedy**
“In Speedy, we used Azure DevOps for our CI/CD process, with Docker and Helm for application packaging and deployment into AKS.We followed a controlled deployment approach and used rolling deployments so that applications could be updated without unnecessary downtime.Before and during the deployment, we monitored the application health, availability, latency and error rates. If the new version showed unexpected behaviour, we had a rollback approach to return to the last known stable version.After the deployment, I would continue monitoring the application to make sure the new version was stable and meeting the expected reliability levels. The main focus was to make deployments safe, controlled and reliable while minimising production impact.”

****Production incident -1** Resource limites increase and scale the pods ,pod crash,memory issue
“We faced a P1 incident where the application became slow, and users were not able to complete actions like search and booking. I took ownership of the issue and focused on stabilising the system quickly. When I checked the system, I saw that some backend services in AKS were restarting frequently. I reviewed the pod logs and monitoring dashboards and identified that memory usage was exceeding the configured limits. To stabilise the system, I increased the memory limits and scaled the pods, which helped restore the service. Once the system was stable, I worked on tuning the resource configuration and improving autoscaling. I also added alerts for memory usage and pod restarts so that similar issues can be detected earlier. This helped improve system reliability and reduced the chance of similar incidents in future.”

**IMAGE PULL ISSUE -- Invalid image name**

“We had a situation where pods were not starting after a deployment. I checked the pod status and saw it was in ImagePullBackOff state. I looked at the pod events and identified that Kubernetes was not able to pull the container image. The issue was due to incorrect access to the private container registry. I updated the image pull credentials and verified the image name and tag. After that, the pods were able to pull the image and started successfully.
To prevent this in future, we added checks in the deployment process to validate image details and registry access.”

**INCIDENT: MISCONFIGURED DEPLOYMENT CAUSED OUTAGE** “Right after a production deployment, we noticed that users were facing errors and the application was partially unavailable. I checked the monitoring dashboards and saw that error rates had increased immediately after the release. I analysed the deployment changes and identified that an environment variable was misconfigured. To restore service quickly, I rolled back to the previous stable version using the pipeline. Once the system was stable, I fixed the configuration issue and redeployed safely. After that, I added validation checks and approval steps in the pipeline to prevent similar issues in future.”

“Fixing 502 Errors During Deployment”
One incident I handled was fixing 502 errors during deployment. Users were getting 502 errors sometimes after a release. At first, everything looked fine — pods were running and there were no major alerts. I checked the Application Gateway and ingress logs and found that some requests were going to pods that were shutting down. Because of that, those pods were not able to handle the request, and users were seeing errors. To fix this, I made sure the pods stop receiving traffic before shutting down, and I added a small delay so they can finish ongoing requests. After this change, the 502 errors were resolved. We also applied the same fix to other services to avoid similar issues in future.”

----“Liveness checks if the pod is alive. Readiness checks if the pod is ready to receive traffic.” “If liveness fails, Kubernetes restarts the pod.” “If readiness fails, the pod is removed from traffic, but it is not restarted.----

TRAFFIC SPIKE
“During one peak time, traffic suddenly increased and the system started slowing down. It was clear that the system was not scaling fast enough to handle the load. So I quickly scaled the application to handle the traffic and bring things back to normal. After that, I adjusted the autoscaling settings so next time it scales automatically without manual intervention.”

========================================================================================= 
**4. DEPENDENCY FAILURE (VERY REAL)**

“We had an issue where part of the application stopped working because one external service we depend on was failing. I checked and found that the service was timing out. Since we can’t control that service, I added retry logic and a fallback so users can still continue without being blocked. After that, we made the system more resilient so external failures don’t affect users too much.”

**🎯 PIPELINE FAILURE DURING DEPLOYMENT (AKS)**

“We had a situation where the pipeline was running fine until the deployment stage, but it failed while deploying to AKS. I checked the deployment logs and saw that the application was not pulling the container image. After checking further, I found there was an issue with the image access from the container registry. I fixed the permissions so the cluster could access the image, and then reran the deployment. After that, the deployment worked successfully. I also added a check in the pipeline to make sure the image is available before deployment

**INGRESS ISSUE – APPLICATION NOT ACCESSIBLE**

“We had a situation where the application was running, but users were not able to access it. I took responsibility to identify the issue quickly. I checked the ingress configuration and found it was pointing to the wrong service. I corrected the configuration and applied the changes. After that, the application became accessible. We also added checks to avoid such configuration issues in future.”

Speedy monitoring aaproach “In our project, I follow a layered monitoring approach using Azure Monitor, Prometheus, Grafana, and Application Insights. At the application level, I use Application Insights to track latency, error rates, and request performance. At the Kubernetes level, I use Prometheus to collect metrics like pod CPU, memory, request rate, and error rate, and Grafana to visualise these metrics through dashboards. At the infrastructure level, I use Azure Monitor to track AKS node-level metrics such as CPU, memory, and overall node health.

I usually approach observability by combining metrics, logs, and traces so I can get a complete picture of what’s happening in the system. When I build dashboards, I don’t just focus on infrastructure metrics like CPU or memory — I try to make them more meaningful by including application-level metrics as well. So typically, I track things like latency, error rates, and request throughput, because those directly reflect user experience. This way, the dashboards show not just system health, but also how users are being impacted, which helps us take quicker and more relevant decision

In different scenarios, I have seen different types of issues:

In one case, I observed high CPU usage on nodes using Azure Monitor. This indicated node-level pressure, so I scaled nodes. In another case, I saw pods going into CrashLoopBackOff, which I identified using Prometheus and logs. This was due to memory limits, and I fixed it by tuning resources. In one situation, there was high latency, but CPU was normal. Using Application Insights, I found it was due to a slow API dependency. I also faced a case where traffic was not routing properly, which I identified as an ingress configuration issue.

So based on the issue, I correlate data from Azure Monitor, Prometheus, and Grafana to identify whether the problem is at node level, pod level, or application level, and take appropriate action. This approach helps me quickly identify and resolve infrastructure issues.”

**CI CD process in speedy**

“In our Speedy project, we use Azure DevOps for CI and ArgoCD for CD to automate our deployments. The process starts when a developer commits code to the repository, which triggers the pipeline automatically. In the build stage, we compile the application and run unit tests to make sure the code is stable. After that, we run SonarQube scans to check code quality and security issues. Once everything passes, we build Docker images for the backend services and push them to Azure Container Registry. Then we update the image version in the Helm chart.

For deployment, we use ArgoCD, which pulls the latest configuration and deploys the application to AKS. We use rolling updates so that new pods are created gradually while old ones are removed, ensuring no downtime. After deployment, we monitor the application using Application Insights, Azure Monitor, and Grafana to ensure everything is working properly. This setup helps us achieve automated, consistent, and reliable deployments.”

🚀 🧠 TERRAFORM SCENARIO (SCRIPTED)

One time, a Terraform deployment failed because the state file was locked during execution.

I checked the backend configuration in S3 and DynamoDB, identified the lock issue, safely released the lock, and re-ran the deployment successfully.

After that, I validated the infrastructure changes and ensured the environment was stable.

🚀 🧠 AWS SCENARIO (SCRIPTED)

We once faced a high CPU utilisation issue on an AWS-hosted application server.

I checked CloudWatch metrics and application logs, identified abnormal traffic and increased resource consumption, and temporarily scaled the environment to stabilise the application.

Later, we optimised the application and monitoring thresholds to avoid recurrence.

🚀 🧠 LINUX SCENARIO (SCRIPTED)

One production server became slow due to disk space reaching critical levels.

I logged into the server, analysed disk usage and large log files using Linux commands, cleaned unnecessary files, and restarted impacted services.

After cleanup, the server performance returned to normal.

🚀 🧠 DOCKER SCENARIO (SCRIPTED)

We had a Docker container repeatedly restarting in production.

I checked the container logs and identified a configuration issue related to environment variables.

After correcting the configuration, I redeployed the container and validated application health.

🚀 🧠 MONITORING / ALERTING SCENARIO (SCRIPTED)

During monitoring, we received alerts for increased latency and error rate in production.

I checked dashboards, correlated metrics with logs, and identified the impacted service.

We stabilised the application quickly and later improved alert thresholds and dashboard visibility for better detection.

🚀 🧠 APACHE / PHP SCENARIO (SCRIPTED)

After one deployment, the application became inaccessible due to an Apache configuration issue.

I validated the Apache configuration, corrected the issue, restarted the service, and confirmed application availability.

🚀 🧠 AUTOMATION SCENARIO (SCRIPTED)

I worked on automating repetitive operational tasks using Bash and Python scripts, such as log cleanup, health checks, and service validation tasks.

This helped reduce manual effort and improved operational efficiency.

BARCALYS VALUES “I believe in ownership, transparency, and continuous improvement.”
Pipeline stuck in queue

“Once the pipeline was stuck in queue for a long time. I checked the agent pool and saw there were no available agents. I added more agents, and it started running.

Pipeline suddenly became slow (after months working fine)

“Our pipeline was running fine earlier, but suddenly it started taking more time. I checked and saw a new step added recently was downloading large files every time. I optimized it using caching and removed unnecessary downloads. That reduced the pipeline time.”

Observability SLI is what we measure, SLO is the target we set, and SLA is the commitment to customers. Error Rate = How many failed ❌ Error rate means how many requests are failing compared to total requests. Latency = How slow 🐢 Latency means how long a request takes to respond. Latency → Graph (speed)
Error → % failures
Traffic → load

🧠DAILY ACTIVITIES (OBSERVABILITY / SRE) Monitor production systems using Prometheus and Grafana dashboards Track golden signals like latency, error rate, traffic, and saturation Check alerts regularly and validate service health status Analyse logs to troubleshoot application and infrastructure issues Correlate metrics, logs, and traces during incidents Handle P1/P2 incidents and join bridge calls Identify root cause and support quick resolution Perform RCA and document findings Tune alert thresholds to reduce alert fatigue Add new alerts based on recurring issues Monitor Kubernetes health (pods, restarts, crash loops, readiness) Investigate memory, CPU, and performance issues Support deployments and monitor post-release behaviour Roll back deployments if critical issues occur Define and track SLIs, SLOs, and error budgets Improve dashboards to make them more actionable Work with developers to improve instrumentation (metrics/logs/traces) Automate repetitive monitoring and operational tasks Continuously improve observability based on incidents

Deployment Stuck - During a deployment, new pods were not becoming ready due to a misconfigured health check.We identified the issue and rolled back to the previous stable version to restore service.
No Traffic to Pods - Pods were running but not receiving traffic because the readiness probe was failing.After fixing the health endpoint, traffic was routed correctly.
Pods Restarting (CrashLoopBackOff) Pods were continuously restarting due to an application configuration issue.We checked logs, fixed the configuration, and stabilized the service.
Service Not Working - The service was not routing traffic due to a label mismatch between service and pods.Once corrected, communication between components was restored.
Ingress Not Working - External traffic was not reaching the application because of incorrect ALB health check configuration.After updating the health check path, routing worked properly.
HPA Not Scaling - The application did not scale during high load because metrics were not available.After fixing the metrics configuration, auto-scaling started working.
ConfigMap Issue -Application was using outdated configuration because pods were not restarted after ConfigMap update.Restarting the pods applied the new configuration successfully.
Image Pull Issue - Pods failed to start due to incorrect image tag or registry access issue.After correcting the image reference and permissions, deployment succeeded.
PDB Blocking Deployment -Deployment was blocked because PodDisruptionBudget was too strict. Adjusting it allowed smooth deployment while maintaining availability.
🎯 🎤 FULL PRODUCTION FLOW (USER → SPEEDY APPLICATION) 👉 User → Internet → WAF → App Gateway → Ingress → AKS Pods → Secure Services → Response

“In our project, the user request follows a secure end-to-end flow. When a user accesses the application, the request first comes through the internet and reaches the WAF layer, where any malicious traffic is filtered. From there, the request goes to the Application Gateway, which handles routing and load balancing. Then it is forwarded to the Kubernetes ingress controller, which routes the request to the appropriate service inside AKS. Within AKS, the request is handled by the application pods running in multiple replicas. These pods communicate with backend services like databases using secure connections. Finally, the response is sent back to the user through the same path. This setup ensures both security and high availability of the application.”

“We also use private networking so backend services are not exposed directly to the internet.”

🎯 🧠 TOOL vs ALERT MAPPING (VERY IMPORTANT) 🟢 APPLICATION INSIGHTS (APP LEVEL)

👉 Used for: API latency ,5xx errors,Failed requests,Timeouts exceptions,Dependency failures (API to API calls) 👉 Example: “Search API slow → App Insights alert”

🔵 PROMETHEUS + GRAFANA (K8s LEVEL)

👉 Used for: Pod CPU usage ,Memory usage,Pod restarts (CrashLoopBackOff),Pod not ready,Container crashes,High API latency (if exposed via metrics) 👉 Example: “Pods high CPU → Prometheus alert”

🟣 AZURE MONITOR (INFRA LEVEL)

👉 Used for: Alerts: Node CPU > 75%,Node memory pressure ,Disk usage high (>80%) ,VM / node not available,Network latency ,AKS node pool scaling issues

👉 Example: “Node overloaded → Azure Monitor alert”

👉 P1 → Users impacted 👉 P2 → Warning / performance issue =------------------------------------------------------------------------

Observability
👉 Strong answer structure: I usually approach observability by combining metrics, logs, and traces so I can get a complete picture of what’s happening in the system. When I build dashboards, I don’t just focus on infrastructure metrics like CPU or memory — I try to make them more meaningful by including application-level metrics as well. So typically, I track things like latency, error rates, and request throughput, because those directly reflect user experience. This way, the dashboards show not just system health, but also how users are being impacted, which helps us take quicker and more relevant decisions.

Application Insights 👉 API errors, 500 errors, latency, timeouts Azure Monitor 👉 Node CPU, memory, VM health Prometheus + Grafana 👉 Pod CPU, restarts, scaling
****2.Grafana Depth
In Grafana, I’ve worked on building dashboards mainly around the golden signals — latency, traffic, errors, and saturation. But I don’t stop there — I also include service-specific metrics depending on the application, like API success rate or request throughput. The idea is to make the dashboard useful for teams, so they can quickly understand whether an issue is coming from the application side or from infrastructure. I also configure alerts based on key thresholds like error rate or latency, so we can detect issues early and respond quickly. Overall, the goal is to make dashboards actionable, so teams can use them during incidents to quickly identify and resolve problems.****

SLI → Service Level Indicator --> is what we measure, like latency or error rate. SLO → Service Level Objectiveis the target we set for those metrics. SLA → Service Level Agreement is the commitment we give to customers. Error budget is the acceptable level of failure based on the SLO.

In practice, I use SLOs to guide decisions — if we start consuming error budget too quickly, we prioritise stability over new releases. “In Grafana, especially with Kubernetes dashboards like 3662, I get a full view of cluster health including node metrics, pod performance, CPU and memory usage, pod restarts, and traffic.

This helps me quickly identify whether the issue is at node level, pod level, or due to load.”

What are golden signals?” 👉 Must say: Latency Traffic Errors Saturation
“How do you reduce alert fatigue?” “By focusing alerts on actionable signals tied to SLO breaches rather than raw metrics. I also regularly review alert noise and tune thresholds or remove low-value alerts.” (Alert fatigue happens when there are too many alerts, especially ones that are not actionable. Over time, teams start ignoring them, which increases the risk of missing important issues.To reduce alert fatigue, I focus on creating alerts that are meaningful and tied to user impact, like high error rates or latency.)

Basket API failure → Dependency issue → Checked logs, fixed pricing/DB service, restored API Order failure after payment → D365 integration issue → Rolled back, fixed integration, reprocessed orders Database connection issue → Connectivity failure → Validated DB/network, restored connection Error rate spike after deployment → Buggy release → Rolled back immediately, fixed and redeployed Latency spike → Slow DB/API → Identified bottleneck, scaled or optimised queries Depot allocation failure → Logic/DB issue → Analysed logs, fixed allocation logic Alert fatigue → Too many noisy alerts → Tuned thresholds, removed non-actionable alerts Config change impact → Incorrect business config → Validated change, monitored, fixed config Downstream API failure → External service down → Implemented retries/fallback, monitored closely Timeout issues → Slow dependencies → Increased timeout, optimised service performance High CPU/memory usage → Resource saturation → Scaled pods using HPA, optimised usage Pod crash loop → App/config error → Checked logs, fixed config, restarted pods Service unavailable (503) → Service down → Restarted pods, checked service endpoints Scaling issue → Traffic spike → Enabled auto-scaling to handle load

Error rates follow in speedy We usually aim for very low error rates, especially for customer-facing APIs — typically below 1%, and even lower for critical services like booking or payments. If error rate crosses a certain threshold, like 2–5%, it is treated as a serious issue and requires immediate attention. For example, in our Speedy application, if the booking API receives 1000 requests and 80 fail due to a backend issue, the error rate becomes 8%, which indicates a serious problem impacting users.

🚀 📊 B. MULTI-LAYER OBSERVABILITY

👉 What to say

We implemented observability at multiple layers:

Application (API metrics) Infrastructure (CPU, memory) Kubernetes (pods, nodes)

.

High Error Rate After Deployment
👉 Answer

After a deployment, we observed an increase in error rate in Grafana dashboards. We checked logs and found a configuration issue, so we rolled back the deployment and fixed it.

🚨 2. Latency Suddenly Increased

👉 Answer

We noticed high latency in Grafana using histogram metrics. After analysing logs and dependencies, we identified a slow database query and optimized it.

🚨 3. No Metrics Visible

👉 Answer

Metrics were not visible because the application was not exposing the /metrics endpoint or Prometheus was not scraping correctly. After fixing the configuration, metrics started appearing.

🚨 4. No Alerts Triggered

👉 Answer

An issue occurred but no alert was triggered due to missing or incorrect alert rules. We updated the alert thresholds to ensure proper monitoring.

🚨 5. High CPU Usage

👉 Answer

We detected high CPU usage through Grafana dashboards. HPA scaled the pods automatically, which resolved the performance issue.

🚨 6. Sudden Drop in Traffic

👉 Answer

We observed a drop in request count, indicating a possible upstream issue or routing problem. We checked ingress and service configuration to restore traffic.

🚨 7. Application Down but Pods Running

👉 Answer

Pods were running but not serving traffic due to readiness probe failure. After fixing the health endpoint, traffic resumed.

🚨 8. Memory Leak Issue

👉 Answer

Memory usage gradually increased over time, detected using Grafana metrics. We identified a memory leak in the application and fixed the code.

🚨 9. Alert Noise (Too Many Alerts)

👉 Answer

We had too many alerts due to improper thresholds. We tuned alert rules to reduce noise and focus on actionable alerts.

🚨 10. Slow Response from External API

👉 Answer

Latency increased due to dependency on an external API. We identified this through metrics and implemented retries and timeouts.

🎤 Q1: How did you confirm it was memory issue? ✅ REAL ANSWER

“In one incident, users reported slowness, so I checked Grafana dashboards. I saw memory usage was continuously increasing and hitting the limit, while CPU was stable and network latency was normal. That clearly indicated it was a memory issue and not CPU or network.”

🎤 Q2: How did you ensure it’s not temporary fix? ✅ REAL ANSWER

“Initially, I increased memory to stabilise the service. But I noticed memory kept increasing again after some time. So I took a heap dump and found that objects were not being released properly. We fixed the code, and after that memory usage became stable.”

🎤 Q3: Ingress issue — how it happened? ✅ REAL ANSWER

“In one deployment, the application was not accessible. When I checked ingress, I found it was pointing to the wrong service name due to a misconfiguration in the Helm chart. After fixing it, we added validation in CI/CD to check service names before deployment.”

🎤 Q4: Why pipeline didn’t catch it? ✅ REAL ANSWER

“In one case, the application failed because an environment variable was missing. The pipeline was successful because it only validated build and tests, not runtime configuration. After that, we added config validation and environment checks in the pipeline.”

🎤 Q5: What did you change in autoscaling? ✅ REAL ANSWER

“During a traffic spike, I saw pods were scaling slowly. I checked HPA settings and found thresholds were too high. I reduced CPU threshold and increased max pod count, so scaling happens faster.”

🎤 Q6: How do you decide min/max pods? ✅ REAL ANSWER

“We analysed historical traffic and saw average load requires 3 pods, so we set that as minimum. During peak, it goes up to 10, so we kept max as 10–12 to handle spikes safely.”

🎤 Q7: ImagePullBackOff — how to differentiate? ✅ REAL ANSWER

“In one case, pods failed with ImagePullBackOff. I checked events and saw ‘authentication failed’, which indicated registry permission issue. In another case, it showed ‘image not found’, which was due to wrong tag.”

🎤 Q8: Fix vs root cause? ✅ REAL ANSWER

“During a P1 incident, users were impacted, so I first stabilised the system by scaling pods. Once stable, I analysed logs and dashboards to identify root cause and fixed it permanently.”

🎤 Q9: Alert fatigue? ✅ REAL ANSWER

“We had too many alerts for minor issues. I analysed alerts and noticed many were not actionable. So I tuned thresholds and removed unnecessary alerts, focusing only on critical ones.”

🎤 Q10: Mistake? ✅ REAL ANSWER

“In one deployment, a configuration issue caused application failure. I fixed it quickly, but realised we missed validation. After that, we added pipeline checks to prevent similar issues.”
