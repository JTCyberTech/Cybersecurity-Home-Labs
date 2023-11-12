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


