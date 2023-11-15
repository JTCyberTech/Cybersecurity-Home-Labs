# Introduction Overview:

1. Focus on Software Development Process Tools:

- Lesson explores tools and services supporting modern software development practices.
- Microsoft's comprehensive set of tools for implementing DevOps practices, developing solutions, and saving costs.

2. Overlap in Functionality:

- Tools may seem to overlap in functionality; criteria exploration helps in selecting the right tools.

3. No Formal Prerequisites:

- No formal prerequisites for the course, but some familiarity with DevOps concepts is valuable.

4. Microsoft's Offerings:

- Tools for Source Code Management, automating testing environments, and continuous integration/delivery.

5. Beneficial Familiarity:

- Familiarity with software development lifecycle, Source Code Management, and version control beneficial for understanding tool value.

6. DevOps Objectives:

- DevOps aligns technical teams toward common goals, automating development, maintenance, and deployment.
- Aims to expedite software changes, ensure ongoing deployability, and maintain a high-quality bar.

7. Comprehensive Impact:

- DevOps practices touch every aspect of the company, including collaboration between developers, operations, and QA teams.

8. Mindset Change:

- DevOps requires a fundamental mindset change from top-down, beyond just tool adoption.

9. Tailwind Traders' Situation:

- Tailwind Traders experimented with various processes and tools but lacked an organizational commitment to DevOps.
- No planned coordinated effort to standardize on core tools and processes.
- Recognizes the critical importance of adopting DevOps for future success.

10. Future Lesson Outcome:

- The lesson aims to empower learners to choose software development process tools and services supporting DevOps practices.
- Emphasis on making informed decisions based on understanding the criteria for tool selection.

<h2></h2>

# Understand your product options

1. Azure DevOps Services:

- Suite of services covering every stage of the software development life cycle.
- Azure Boards: Agile project management suite with Kanban boards, reporting, and high-level epics to work items.
- Azure Repos: Centralized source code repository for collaboration and code review.
- Azure Pipelines: Continuous integration and continuous delivery automation tool.
- Azure Test Plans: Automated test tool integrated into CI/CD pipelines.
- Azure Artifacts: Repository for hosting artifacts such as compiled source code.

2. GitHub and GitHub Actions:

- GitHub is a popular code repository for open-source software, built on Git.
- GitHub Actions enables workflow automation with triggers for lifecycle events.
- GitHub offers code repository, code reviews, project management, issue tracking, CICD pipeline automation, wiki, and more.
- GitHub Actions supports automation of continuous integration or continuous delivery toolchains.

3.Choosing Between Azure DevOps and GitHub:

- GitHub has a history with public repositories, trusted by many open-source project owners.
- GitHub is lighter-weight, focused on individual developers contributing to open-source code.
- Azure DevOps is more enterprise-focused with heavier project management tools and fine-grained access control.
- Choices are not limited to one or the other; services can be mixed and matched based on organizational needs.

4. Azure DevTest Labs:

- Aimed at managing VMs for testing and development purposes.
- Provides automated processes for building, setting up, and tearing down virtual machines.
- Enables testing across various operating systems and environments.
- Can provision pre-created lab environments with required configurations and tools.
- Useful for controlling costs by restricting the creation and duration of labs.

5. Working of Azure DevTest Labs:

- Automatically sets up environments for testing upon request.
- Efficiently manages VMs by shutting down and deallocating resources when not in use.
- Allows control over costs by setting restrictions on the creation and duration of labs.

<h2></h2>

# Analyze the decision criteria

1. Criteria for Choosing DevOps Tools:

- Analysis of criteria employed by experts when choosing DevOps tools or services for specific business needs.
- Understanding these criteria aids in discerning nuanced differences between products.

2. Azure DevTest Labs:

- Consideration for automating the creation and management of a test-lab environment.
- Unique functionality offered by Azure DevTest Labs in this context.

3. Automation with Azure Pipelines or GitHub Actions:

- Automation of lab provisioning as part of a tool chain using Azure Pipelines or GitHub Actions.

4.Open Source Software Development:

- Consideration for choosing between Azure DevOps and GitHub, particularly when building open source software.
- GitHub often preferred for its visibility and general acceptance within the open-source development community.

5. Mixing and Matching Services:

- Flexibility to mix and match services as needed, such as using GitHub Repos with Azure Boards for work item tracking.

6. Source Code Management and DevOps Tools - Permissions:

- Consideration of granularity in permissions for source code management.
- GitHub uses a simple model of read-write permissions, while Azure DevOps offers a more granular set of permissions.

7. Source Code Management and DevOps Tools - Project Management:

- Evaluation of project management and reporting capabilities.
- Azure DevOps excels in project management with high customization, allowing the addition of custom fields for metadata alongside work items.
- GitHub relies on tags as the primary means of categorizing issues.

8. Source Code Management and DevOps Tools - Integration with Third-Party Tools:

- Consideration of the need to integrate with third-party tools.
- Importance of understanding existing investments in tools and services within the organization.
- Many DevOps tool vendors provide hooks or APIs usable by both Azure Pipelines and GitHub Actions.

9.Validation of Assumptions:

- Emphasis on validating assumptions about third-party tool integration capabilities.

<h2></h2>

# Manage the application development lifecycle

1. Tailwind Traders Software Development Team:

- Engages in various projects for both internal and external use.
- Requires executive-level reporting, including burned down charts, progress tracking against epics, and custom information for each work item and bug report.

2. Tailwind Traders Growth and Access Control:

- As Tailwind Traders grows and hires contractors and vendors, upper management aims to ensure limited access to necessary information for short-term work.

3. Decision Criteria for DevOps Solution:

- Test Lab Automation:
  - Dev Test Labs is not considered suitable for this specific use case.
- Open Source Software:
  -Tailwind Traders is not building open source software; the focus is on internal and external systems like their e-commerce system.
- Azure DevOps as a Candidate:
  - Granular permissions are crucial for managing temporary employees and vendors.
  - Azure DevOps is a leading candidate due to its granular permissions feature.
  - Provides robust options for controlling permissions across the entire portfolio of work.
- Project Management and Reporting:
  - Robust project management and reporting features are essential for Tailwind Traders.
  - Azure DevOps is likely a good choice based on the customization and reporting requirements.
- Integration with Third-Party DevOps Tools:
  - Tight integration with third-party DevOps tools is not a primary consideration for this scenario.
  - Most third-party DevOps tools integrate with both Azure DevOps and GitHub.

4. Conclusion:

- Considering the expert criteria, Azure DevOps is the recommended service for Tailwind Traders.
- It aligns with the specific needs of Tailwind Traders, offering granular permissions, robust project management and reporting, and potential integration with third-party tools.

<h2></h2>

# Use GitHub to contribute to open-source software

1. Tailwind Traders API Integration:

- Aim to publish an API for third-party integration with inventories of new and used items.
- Goal: Offer a wider variety of products directly from their e-commerce site.

2. API Example Code and Community Building:

- Internal implementation of the API is closed source.
- Desire to create examples calling the API for various actions.
- Need a platform to share example code, collect feedback, report issues, and build a community around feature requests.

3. Decision Criteria:

- Does Tailwind Traders need to automate and manage test lab creation? No.
- Is Tailwind Traders building open source software? Yes.
- Given the granularity of permission needs, is GitHub a good candidate? Yes.
- Does Tailwind Traders require a sophisticated project management and reporting solution? No.
- Does Tailwind Traders require tight integration with any third-party DevOps tools? No.

4. GitHub as the Preferred Choice:

- GitHub is a leading candidate for this scenario due to its compatibility with open source software development.
- Allows publishing code, accepting community contributions, feedback, and bug reports.
- Basic permission needs are met with view-only or view-and-write options.

5. Azure DevOps Services Consideration:

- Azure DevOps Services are not required for this scenario.
- Tailwind Traders doesn't need a sophisticated project management and reporting solution.
- Tight integration with third-party DevOps tools is not a primary consideration.

6. Accessibility and Community Engagement:

- GitHub is preferred for its accessibility to the development community, especially for features like feedback and bug reports.
- While Azure DevOps could make the repository public, some community-oriented features might be less accessible.

In summary, GitHub is the preferred choice for Tailwind Traders in this scenario, aligning well with their open source development needs, basic permission requirements, and community engagement goals.

<h2></h2>

# Use Azure DevTest Labs to manage testing environments

1. Tailwind Traders Objectives:

- Aim to be more methodical and careful when deploying new versions of the e-commerce website to production.
- Expanding the quality assurance team.
- Utilizing the cloud to create and host virtual machines for testing environments matching production.

2. Cloud-Based Testing Environment:

- Using the cloud to host virtual machines for creating testing environments.
- Ensuring testing environments match the production environment.

3. Management Concerns:

- Concerns about the costs of an automated test environment.
- Need to avoid QA professionals wasting time on environment configuration.
- Desire to ensure VMs are destroyed when not in use.
- Limiting the number of VMs each QA professional can spin up.
- Ensuring each environment is configured correctly and consistently with the production environment.

4. Solution: Azure DevTest Labs:

- Decision: Tailwind Traders needs to automate and manage test lab creation.
- Azure DevTest Labs is suitable for the scenario, meeting all the requirements.
- No need for Azure DevOps or GitHub in this specific scenario.

5. Azure DevOps and GitHub:

- Not needed for this particular scenario.
- Can be used for creating product releases that can be automatically included in VMs for testing purposes.

6.Importance of Software Development Services and Tools:

- Acknowledgment that without software development services and tools from Microsoft, Tailwind Traders may face difficulties in realizing the benefits of DevOps practices.
- Mentioned practices include continuous integration, continuous delivery, source code management, and work item management.

<h2></h2>

# Questions:

1. Software developers and operations professionals traditionally work to create software systems that satisfy the needs of the organization. DevOps is a new approach that helps to align technical teams to work towards their common goal. Which of the following provides a suite of services that addresses each stage of the Software Development Lifecycle (SDL)?

`Azure DevOps Services`: Azure DevOps is a suite of services that address every stage of the Software Development Lifecycle (SDL).

2. Which of the following is a shared source code repository that includes tools that enable developers to perform code reviews by adding comments and questions in a web-view of the source code before it is merged into the main code base?

`GitHub and GitHub Actions`: GitHub is one of the most popular code repositories for open-source software. GitHub provides related services for coordinating work, reporting, and discussing issues, providing documentation, and more.

3. True or False

GitHub is “lighter weight” than Azure DevOps, with a focus on individual developers contributing to open source while Azure DevOps, is more focused on enterprise development with heavier project management, planning tools, and finer-grained access control.

`True`: GitHub has a long and trusted history with public repositories and is trusted by tens of thousands of open-source projects. GitHub is “lighter weight” than Azure DevOps, with a focus on individual developers contributing to open source. Azure DevOps, on the other hand, is more focused on enterprise development with heavier project management and planning tools, and finer-grained access control.

4. True or False

Azure DevTestLabs provide automated provisioning of pre-created lab environments with required configurations and tools already installed.

`True`: Azure DevTest Labs allows for the provisioning of pre-created lab environments with required configurations and tools already installed. It is a huge timesaver for quality assurance professionals and developers.

5. In your organization software development teams work on many different projects and they are required to provide project sponsors and managers with reports, progress tracking, bug reports etc. Management wants to ensure that individuals have access to only the information they need to do their work.

Which of the following in your opinion would be the most suitable solution to implement?

`Azure DevOps Services`:  Azure DevOps has a much more granular set of permissions that allow organizations to refine who is able to perform most operations across the entire toolset. Also, Azure DevOps is highly customizable, allowing an administrator to add custom fields to capture metadata and other information alongside each work item. By contrast, GitHub Issues uses tags as its primary means of helping a team categorize issues.

6. Your company wants to publish an open-source API that allows third-parties to integrate their own inventories of new and used items. They also want to use the API to offer a wider variety of products directly from your ecommerce site. You need a platform to share example code, collect feedback on the API, allow contributors to report issues, and build a community around feature requests.

Which of the following do you think is the most suitable solution to implement?

`GitHub and GitHub Actions`: With GitHub, your company can publish its code, accept community contributions to improve the code examples, accept feedback, and bug reports. Because this scenario involves open-source code, GitHub is a leading candidate

<h2></h2>

# Test Prep

1. Artificial Intelligence (AI) is a broad classification of computing that allows a software system to perceive its environment and take action that maximizes its chance of successfully achieving its goals. A goal of AI is to create a software system that is able to adapt or learn something on its own without being explicitly programmed to do it.

One approach to AI is a technique that uses existing data to train and test a model, then apply that model to new data to forecast future behaviors, outcomes, and trends. What is this referred to as?

`Machine Learning`: Machine learning, which is a data science technique uses existing data to train and test a model, then apply that model to new data to forecast future behaviors, outcomes, and trends.

2. There are three primary AI offerings from Microsoft Azure, each of which are designed for a specific audience and use case. Which of the following is a feature of Azure Cognitive Services?

Select all options that apply.

`The ability to convert speech into text and text into natural-sounding speech. Translate from one language to another and enable speaker verification and recognition.`: Speech services is a feature of Azure Cognitive Services that allow the conversion of speech into text and text into natural-sounding speech. 

`The ability to add recognition and identification capabilities when analyzing pictures, videos, and other visual content.`: Vision services provides the ability to add recognition and identification capabilities when analyzing pictures, videos, and other visual content.

3. Your organization requires the following Azure Features: 
Pre-built machine learning models that enable applications to see, hear, speak, understand.

Which service should they avail of?

`Azure Cognitive Services`: Azure Cognitive Services provides pre-built machine learning models that enable applications to see, hear, speak, understand, and even begin to reason.

4. Which of the following provides an automated means of managing the process of building, setting up, and tearing down Virtual Machines?

`Azure DevTest Labs`: Azure DevTest Labs provides an automated means of managing the process of building, setting up, and tearing down Virtual Machines.

5. Your company wants to implement a structured project management and reporting solution in Azure cloud services. Which of the following do you think is the most suitable solution to implement?

`Azure DevOps Services`: Given the nature of this project, requires a sophisticated project management and reporting solution which Azure DevOps is ideal for.

