# Introduction Overview

1. Complexity of Modern Cloud Software Systems:

- Modern cloud-based software systems are complex.
- Gaining visibility into the health and performance of the application hosting environment is challenging due to multiple layers of services.

2. Challenges Faced by Tailwind Traders:

- Tailwind Traders, a traditional retailer, is now growing explosively through online sales.
- Challenges include optimizing cloud spending and security posture, tracking intermittent issues, and planning for upcoming outages.

3. Microsoft Solutions for Cloud Monitoring:

- Microsoft offers several solutions to address challenges in monitoring cloud environments.

4. Objectives of Monitoring Solutions:

- React quickly to outages.
- Research intermittent issues.
- Optimize usage.
- Proactively handle planned downtime.

5. Tailwind Traders' Need for Assistance:

- Tailwind Traders needs help choosing the right product options for optimizing cloud spending, enhancing security posture, tracking intermittent issues, and planning for upcoming outages.

6. Learning Objectives:

- The lesson focuses on Microsoft monitoring solutions.
- Analyzing decision criteria used by experts to select the appropriate service for specific scenarios.

7. Outcome of the Lesson:

- After completing the lesson, individuals will be able to choose the cloud monitoring service that best addresses their company's business challenges.

<h2></h2>

1. Common Concerns for Companies Using the Cloud:

- Correct utilization of the Cloud.
- Optimization of Cloud spending.
- Proper security measures.
- Resilience of resources during regional outages.
- Diagnosing and fixing intermittent issues.
- Quickly determining the cause of outages.
- Awareness of planned downtime.

2. Azure Monitoring Offerings:

- Azure Advisor, Azure Monitor, Azure Service Health.
- Aimed at specific audiences and use cases.
- Provides tools, services, programmatic APIs, and more.

3. Azure Advisor:

- Evaluates Azure resources and offers recommendations.
- Improves reliability, security, performance, operational excellence, and reduces costs.
- Recommendation is there at the Azure Portal and the API
- Dashboard displays personalized recommendations in five categories: reliability, security, performance, cost, operational excellence.
  - Realiability: used to ensure and improve the continuity of your business critical applications.
  - Security: used to detect threats and vulnerabilities that might lead to security breaches.
  - Performance: used to improve the speed of yout applications.
  - Cost: used to optimize and reduce your overall Azure spending.
  - Operational Excellence: used to help you achieve process and workflow efficiency, resource managebility and deployment best practices.

4. Azure Monitor:

- Platform for collecting, analyzing, visualizing, and taking action based on metric and logging data.
- Comprehensive coverage across the entire Azure and on-premises environment.
- Real-time and historical performance monitoring at different levels.
- Alerts for critical events, auto-scaling functionality, integration with popular products like Azure Application Insights.

5. Azure Service Health:

- Notifies about Azure service incidents and planned maintenance.
- Personalized view of Azure services, regions, and resources health.
- Displays both major and smaller localized issues.
- Provides health advisories for proactive action.
- Keeps track of planned maintenance events with details on affected services, regions, and impact.

6. Event Types Monitored by Service Health:

- Service Issues: Immediate problems affecting Azure.
- Health Advisories: Advance notice for planned changes or retirements.
- Planned Maintenance: Track events that might affect availability.
- Official incident reports (Root Cause Analysis or RCA) shared after an outage.

7. Service Health Features:

- Alerts: Set up to triage outages and planned maintenance.
- Drill Down: Detailed information on affected services, regions, and updates.
- Reboot Management: Choose when to perform maintenance to minimize downtime.

<h2></h2>

# Analyze the decision criteria

1. Criteria for Choosing Azure Monitoring Service:

- Experts consider specific criteria when choosing an Azure monitoring service for a business need.
- Understanding these criteria helps assess nuanced differences among products.

2. Azure Advisor:

- Useful for projects where cost reduction, improving resilience, or enhancing security are important considerations.
- Analyzes deployed resources, configurations, and usage.
- Provides suggestions for optimization based on best practices in reliability, security, performance, costs, and operations.

3. Azure Service Health:

- Monitors Azure itself, focusing on the services and regions critical to your project.
- Displays the current status of Azure services, upcoming planned outages, and services scheduled for sunset.
- Allows setting up alerts for instances and upcoming downtime without regular dashboard visits.

4. Azure Monitor:

- Tracks performance or issues related to specific VM or container instances, databases, and applications.
- Enables the creation of reports and notifications to understand service performance or diagnose Azure-related issues.
- Suitable for measuring custom events alongside other usage metrics.
- Enables setting up alerts for outages or autoscaling events, specifically tailored to your resources.
- Ideal for measuring custom events added in the source code of software applications to identify and diagnose application behavior.

<h2></h2>

# User Azure Advisor

1. Tailwind Traders Objectives:

- Optimization of Cloud spending.
- Concerns about security breaches due to storing customer and historical purchase data in cloud-based databases.
- Desire to better understand and improve Cloud usage, following best practices.

2.Decision Criteria:

- Focus on analyzing Cloud usage against industry best practices.
- Concerns about overspending and security practices.
- Selection of Azure Advisor as the best option for the scenario.

3.Azure Advisor Suitability:

- Tailwind Traders acknowledges potential overspending and security concerns.
- Azure Advisor identified as the best solution for analyzing Cloud usage against industry best practices.

4.Additional Evaluation:

- Confirmation that Tailwind Traders doesn't need to monitor the health of Azure services affecting all customers or resources deployed in Azure for this scenario.
- Azure Advisor's capability to analyze and provide recommendations for achieving operational excellence acknowledged, even though not a primary concern.

5. Custom Event Measurement:

- Tailwind Traders doesn't express a need to measure custom events alongside other usage metrics in this scenario.

6. Alerts and Operations:

- Scenario not concerned with operations or setting up alerts for outages or auto-scaling instances.
- Azure Advisor's capability to provide recommendations for achieving operational excellence is noted.

7. Conclusion:

- Azure Advisor identified as the right product option to help Tailwind Traders understand and optimize both its Cloud spending and security posture.
- Potential for Azure Advisor to assist in other areas of Cloud usage as well.

<h2></h2>

# Use Azure Monitor

1. Issue Overview:

- Tailwind Traders e-commerce website experiencing intermittent errors.
- Team suspects it's either a database or caching issue.
- Uncertain about circumstances: occurrence during peak times, Azure SQL instance status, and tracing the root cause.

2. Decision Criteria:

- Applying decision criteria to find the right option.
- Optimization not the objective, so Azure Advisor isn't a candidate.
- Intermittent issue unlikely to affect entire Azure region or service.

3. Option Consideration: Azure Monitor:

- Azure Monitor is considered for pinpointing specific user sessions and analyzing service performance.
- Tailwind Traders can use Azure Monitor tools to gain insights into application performance at both high and detailed levels.

4. Tailwind Traders' Objective:

- Team wants to measure custom events alongside other usage metrics.
- Application insights can be used to send additional information about the web application's stage for locating the root cause.
- Application insights relies on Azure Monitor to store custom event information.

5. Alerting Consideration:

- Tailwind Traders does not want to set up alerts for outages or auto-scaling deployment in this scenario.
- Azure Monitor is deemed the best option for tracking the intermittent issue.

6. Conclusion:

- Azure Monitor is identified as the preferred option for helping Tailwind Traders track and resolve the intermittent issue.
- Offers a range of tools for gaining insights into application performance and deep diving into specific issues.
- Custom event measurement via Application Insights and integration with Azure Monitor considered beneficial for root cause analysis.

<h2></h2>

# Use  Azure Service Health

1. Tailwind Traders' Cloud Operational Goals:

- Operationalize the cloud environment.
- Notify stakeholders about upcoming planned downtime.
- Be informed about Microsoft's plans to sunset services.
- Quickly ascertain the nature of outages (specific to their services or affecting many Azure customers).
- Provide stakeholders with detailed incident reports.

2. Decision Criteria for Choosing a Monitoring Service:

- Azure Usage Analysis: Not needed for optimization, so Azure Advisor is not a candidate.
- Monitoring Health of Azure Services: Important for staying informed about planned downtime and capturing incident reports.
- Measuring Custom Events: Not mentioned as a requirement, so not considered in this scenario.

3. Evaluation of Decision Criteria:

- Azure Service Health: Strong candidate for monitoring health, providing alerts for Azure outages affecting all customers, and capturing official incident reports.

4. Alerting Requirements:

- Azure Service Health can be used to set up alerts for Azure outages affecting all customers.
- Azure Monitor can be used to set up alerts for outages and other events specific to Tailwind Traders' resources.

5. Completion of the Lesson:

- Tailwind Traders explored monitoring service offerings: Azure Advisor, Azure Monitor, and Azure Service Health.
- Decision criteria were analyzed and applied to three challenges faced by Tailwind Traders.
- Azure Service Health was chosen as the best service option for the given scenario.
- Without monitoring services, Tailwind Traders could face increased costs, uncertainty about cloud security, difficulty pinpointing issues, and inability to plan for outages or provide formal outage reports to stakeholders.
- Azure monitoring services offer a comprehensive array of features to improve cloud operations.

<h2></h2>

# Questions 

1. Which of Azure’s three primary monitoring offerings are most useful for collecting, analyzing, visualizing, and possibly taking actions based on the collected data from your entire Azure and on-premises environment?

`Azure Monitor`: Azure Monitor is a platform for collecting, analyzing, visualizing, and potentially taking action based on the metric and logging data from your entire Azure and on-premises environment.

2. Which of Azure’s three primary monitoring offerings are most useful for providing a personalized view of the health of the Azure services, regions, and resources?

`Azure Service Health`: Azure Service Health provides a personalized view of the health of the Azure services, regions, and resources.

3. You need to optimize your cloud services for reliability, security, performance, costs, and operations based on expert best practices. Which Azure monitoring tool would you recommend to best satisfy this requirement?

`Azure Advisor`: Azure Advisor evaluates your Azure resources and makes recommendations to help you improve reliability, security, and performance, achieve operational excellence, and reduce costs.

4. You have been tasked with creating alerts that will send notifications to your department when Azure outages occur. Which Azure monitoring tool would you recommend to do this?

`Azure Monitor`: Azure Monitor is a platform for collecting, analyzing, visualizing, and potentially taking action based on the metric and logging data from your entire Azure and on-premises environment.

5. Question 5
Your company has recently moved to Azure cloud services. Management are concerned that they may be spending too much and have also highlighted how well their new environment meet security best practices. They would like to analyze their use of the cloud analyzed against industry best practices. Which monitoring tool would you recommend using for this?

`Azure Advisor`:Azure Advisor evaluates your Azure resources and makes recommendations to help you improve reliability, security, and performance, achieve operational excellence, and reduce costs.
