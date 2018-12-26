

Performance testing is a type of testing intended to determine the responsiveness, throughput, reliability, and/or scalability of a system under a given workload. 

Performance testing is commonly conducted to accomplish the following:
* Assess production readiness
* Evaluate against performance criteria
* Compare performance characteristics of multiple systems or system configurations
* Find the source of performance problems
* Support system tuning
* Find throughput levels

Performance testing is typically done to help identify bottlenecks in a system, establish a baseline for future testing, support a performance tuning effort, determine compliance with performance goals and requirements, and/or collect other performance-related data to help stakeholders make informed decisions related to the overall quality of the application being tested. In addition, the results from performance testing and analysis can help you to estimate the hardware configuration required to support the application(s) when you “go live” to production operation.

# Core Activities of Performance Testing
![1](https://docs.microsoft.com/en-us/previous-versions/msp-n-p/images/bb924375.image001%28en-us%2cpandp.10%29.gif)

The performance testing approach used in this guide consists of the following activities:

* Activity 1. Identify the Test Environment. Identify the physical test environment and the production environment as well as the tools and resources available to the test team. The physical environment includes hardware, software, and network configurations. Having a thorough understanding of the entire test environment at the outset enables more efficient test design and planning and helps you identify testing challenges early in the project. In some situations, this process must be revisited periodically throughout the project’s life cycle.
* Activity 2. Identify Performance Acceptance Criteria. Identify the response time, throughput, and resource utilization goals and constraints. In general, response time is a user concern, throughput is a business concern, and resource utilization is a system concern. Additionally, identify project success criteria that may not be captured by those goals and constraints; for example, using performance tests to evaluate what combination of configuration settings will result in the most desirable performance characteristics.
* Activity 3. Plan and Design Tests. Identify key scenarios, determine variability among representative users and how to simulate that variability, define test data, and establish metrics to be collected. Consolidate this information into one or more models of system usage to be implemented, executed, and analyzed.
* Activity 4. Configure the Test Environment. Prepare the test environment, tools, and resources necessary to execute each strategy as features and components become available for test. Ensure that the test environment is instrumented for resource monitoring as necessary.
* Activity 5. Implement the Test Design. Develop the performance tests in accordance with the test design.
* Activity 6. Execute the Test. Run and monitor your tests. Validate the tests, test data, and results collection. Execute validated tests for analysis while monitoring the test and the test environment.
* Activity 7. Analyze Results, Report, and Retest. Consolidate and share results data. Analyze the data both individually and as a cross-functional team. Reprioritize the remaining tests and re-execute them as needed. When all of the metric values are within accepted limits, none of the set thresholds have been violated, and all of the desired information has been collected, you have finished testing that particular scenario on that particular configuration.


# Why Do Performance Testing?
At the highest level, performance testing is almost always conducted to address one or more risks related to expense, opportunity costs, continuity, and/or corporate reputation. Some more specific reasons for conducting performance testing include:

## Assessing release readiness by:
* Enabling you to predict or estimate the performance characteristics of an application in production and evaluate whether or not to address performance concerns based on those predictions. These predictions are also valuable to the stakeholders who make decisions about whether an application is ready for release or capable of handling future growth, or whether it requires a performance improvement/hardware upgrade prior to release.
* Providing data indicating the likelihood of user dissatisfaction with the performance characteristics of the system.
* Providing data to aid in the prediction of revenue losses or damaged brand credibility due to scalability or stability issues, or due to users being dissatisfied with application response time.

## Assessing infrastructure adequacy by:
* Evaluating the adequacy of current capacity.
* Determining the acceptability of stability.
* Determining the capacity of the application’s infrastructure, as well as determining the future resources required to deliver acceptable application performance.
* Comparing different system configurations to determine which works best for both the application and the business.
* Verifying that the application exhibits the desired performance characteristics, within budgeted resource utilization constraints.

## Assessing adequacy of developed software performance by:
* Determining the application’s desired performance characteristics before and after changes to the software.
* Providing comparisons between the application’s current and desired performance characteristics.

## Improving the efficiency of performance tuning by:
* Analyzing the behavior of the application at various load levels.
* Identifying bottlenecks in the application.
* Providing information related to the speed, scalability, and stability of a product prior to production release, thus enabling you to make informed decisions about whether and when to tune the system.

# Baselines
* Creating a baseline is the process of running a set of tests to capture performance metric data for the purpose of evaluating the effectiveness of subsequent performance-improving changes to the system or application. A critical aspect of a baseline is that all characteristics and configuration options except those specifically being varied for comparison must remain invariant. Once a part of the system that is not intentionally being varied for comparison to the baseline is changed, the baseline measurement is no longer a valid basis for comparison.
* With respect to Web applications, you can use a baseline to determine whether performance is improving or declining and to find deviations across different builds and versions. For example, you could measure load time, the number of transactions processed per unit of time, the number of Web pages served per unit of time, and resource utilization such as memory usage and processor usage. Some considerations about using baselines include:
* A baseline can be created for a system, component, or application. A baseline can also be created for different layers of the application, including a database, Web services, and so on.
* A baseline can set the standard for comparison, to track future optimizations or regressions. It is important to validate that the baseline results are repeatable, because considerable fluctuations may occur across test results due to environment and workload characteristics.
* Baselines can help identify changes in performance. Baselines can help product teams identify changes in performance that reflect degradation or optimization over the course of the development life cycle. Identifying these changes in comparison to a well-known state or configuration often makes resolving performance issues simpler.
* Baselines assets should be reusable. Baselines are most valuable if they are created by using a set of reusable test assets. It is important that such tests accurately simulate repeatable and actionable workload characteristics.
* Baselines are metrics. Baseline results can be articulated by using a broad set of key performance indicators, including response time, processor capacity, memory usage, disk capacity, and network bandwidth.
* Baselines act as a shared frame of reference. Sharing baseline results allows your team to build a common store of acquired knowledge about the performance characteristics of an application or component.
* Avoid over-generalizing your baselines. If your project entails a major reengineering of the application, you need to reestablish the baseline for testing that application. A baseline is application-specific and is most useful for comparing performance across different versions. Sometimes, subsequent versions of an application are so different that previous baselines are no longer valid for comparisons.
* Know your application’s behavior. It is a good idea to ensure that you completely understand the behavior of the application at the time a baseline is created. Failure to do so before making changes to the system with a focus on optimization objectives is frequently counterproductive.
Baselines evolve. At times you will have to redefine your baseline because of changes that have been made to the system since the time the baseline was initially captured.

# Benchmarking
* Benchmarking is the process of comparing your system’s performance against a baseline that you have created internally or against an industry standard endorsed by some other organization.
* In the case of a Web application, you would run a set of tests that comply with the specifications of an industry benchmark in order to capture the performance metrics necessary to determine your application’s benchmark score. You can then compare your application against other systems or applications that also calculated their score for the same benchmark. You may choose to tune your application performance to achieve or surpass a certain benchmark score. Some considerations about benchmarking include:
* You need to play by the rules. A benchmark is achieved by working with industry specifications or by porting an existing implementation to meet such standards. Benchmarking entails identifying all of the necessary components that will run together, the market where the product exists, and the specific metrics to be measured.
* Because you play by the rules, you can be transparent. Benchmarking results can be published to the outside world. Since comparisons may be produced by your competitors, you will want to employ a strict set of standard approaches for testing and data to ensure reliable results.
* You divulge results across various metrics. Performance metrics may involve load time, number of transactions processed per unit of time, Web pages accessed per unit of time, processor usage, memory usage, search times, and so on.


# Tuning Process Overview
* Tuning follows an iterative process that is usually separate from, but not independent of, the performance testing approach a project is following. The following is a brief overview of a typical tuning process:
* Tests are conducted with the system or application deployed in a well-defined, controlled test environment in order to ensure that the configuration and test results at the start of the testing process are known and reproducible.
* When the tests reveal performance characteristics deemed to be unacceptable, the performance testing and tuning team enters a diagnosis and remediation stage (tuning) that will require changes to be applied to the test environment and/or the application. It is not uncommon to make temporary changes that are deliberately designed to magnify an issue for diagnostic purposes, or to change the test environment to see if such changes lead to better performance.
* The cooperative testing and tuning team is generally given full and exclusive control over the test environment in order to maximize the effectiveness of the tuning phase.
* Performance tests are executed, or re-executed after each change to the test environment, in order to measure the impact of a remedial change.
* The tuning process typically involves a rapid sequence of changes and tests. This process can take exponentially more time if a cooperative testing and tuning team is not fully available and dedicated to this effort while in a tuning phase.
* When a tuning phase is complete, the test environment is generally reset to its initial state, the successful remedial changes are applied again, and any unsuccessful remedial changes (together with temporary instrumentation and diagnostic changes) are discarded. The performance test should then be repeated to prove that the correct changes have been identified. It might also be the case that the test environment itself is changed to reflect new expectations as to the minimal required production environment. This is unusual, but a potential outcome of the tuning effort.


# Project Context
For a performance testing project to be successful, both the approach to testing performance and the testing itself must be relevant to the context of the project. Without an understanding of the project context, performance testing is bound to focus on only those items that the performance tester or test team assumes to be important, as opposed to those that truly are important, frequently leading to wasted time, frustration, and conflicts.

The project context is nothing more than those things that are, or may become, relevant to achieving project success. This may include, but is not limited to:
* The overall vision or intent of the project
* Performance testing objectives
* Performance success criteria
* The development life cycle
* The project schedule
* The project budget
* Available tools and environments
* The skill set of the performance tester and the team
* The priority of detected performance concerns
* The business impact of deploying an application that performs poorly
* Some examples of items that may be relevant to the performance-testing effort in your project context include:

* **Project vision.** Before beginning performance testing, ensure that you understand the current project vision. The project vision is the foundation for determining what performance testing is necessary and valuable. Revisit the vision regularly, as it has the potential to change as well.
* **Purpose of the system.** Understand the purpose of the application or system you are testing. This will help you identify the highest-priority performance characteristics on which you should focus your testing. You will need to know the system’s intent, the actual hardware and software architecture deployed, and the characteristics of the typical end user.
* **Customer or user expectations.** Keep customer or user expectations in mind when planning performance testing. Remember that customer or user satisfaction is based on expectations, not simply compliance with explicitly stated requirements.
* **Business drivers.** Understand the business drivers – such as business needs or opportunities – that are constrained to some degree by budget, schedule, and/or resources. It is important to meet your business requirements on time and within the available budget.
* **Reasons for testing performance.** Understand the reasons for conducting performance testing very early in the project. Failing to do so might lead to ineffective performance testing. These reasons often go beyond a list of performance acceptance criteria and are bound to change or shift priority as the project progresses, so revisit them regularly as you and your team learn more about the application, its performance, and the customer or user.
* **Value that performance testing brings to the project.** Understand the value that performance testing is expected to bring to the project by translating the project- and business-level objectives into specific, identifiable, and manageable performance testing activities. Coordinate and prioritize these activities to determine which performance testing activities are likely to add value.
* **Project management and staffing.** Understand the team’s organization, operation, and communication techniques in order to conduct performance testing effectively.
* **Process.** Understand your team’s process and interpret how that process applies to performance testing. If the team’s process documentation does not address performance testing directly, extrapolate the document to include performance testing to the best of your ability, and then get the revised document approved by the project manager and/or process engineer.
* **Compliance criteria.** Understand the regulatory requirements related to your project. Obtain compliance documents to ensure that you have the specific language and context of any statement related to testing, as this information is critical to determining compliance tests and ensuring a compliant product. Also understand that the nature of performance testing makes it virtually impossible to follow the same processes that have been developed for functional testing.
* **Project schedule.** Be aware of the project start and end dates, the hardware and environment availability dates, the flow of builds and releases, and any checkpoints and milestones in the project schedule.


# Key Types of Performance Testing

* **Performance test** - To determine or validate speed, scalability, and/or stability.
* A performance test is a technical investigation done to determine or validate the responsiveness, speed, scalability, and/or stability characteristics of the product under test.

* **Load test** - To verify application behavior under normal and peak load conditions.
* Load testing is conducted to verify that your application can meet your desired performance objectives; these performance objectives are often specified in a service level agreement (SLA). A load test enables you to measure response times, throughput rates, and resource-utilization levels, and to identify your application’s breaking point, assuming that the breaking point occurs below the peak load condition.
* Endurance testing is a subset of load testing. An endurance test is a type of performance test focused on determining or validating the performance characteristics of the product under test when subjected to workload models and load volumes anticipated during production operations over an extended period of time.
* Endurance testing may be used to calculate Mean Time Between Failure (MTBF), Mean Time To Failure (MTTF), and similar metrics.


* **Stress test** - To determine or validate an application’s behavior when it is pushed beyond normal or peak load conditions.
* The goal of stress testing is to reveal application bugs that surface only under high load conditions. These bugs can include such things as synchronization issues, race conditions, and memory leaks. Stress testing enables you to identify your application’s weak points, and shows how the application behaves under extreme load conditions.
* Spike testing is a subset of stress testing. A spike test is a type of performance test focused on determining or validating the performance characteristics of the product under test when subjected to workload models and load volumes that repeatedly increase beyond anticipated production operations for short periods of time.

* **Capacity test** - To determine how many users and/or transactions a given system will support and still meet performance goals.
* Capacity testing is conducted in conjunction with capacity planning, which you use to plan for future growth, such as an increased user base or increased volume of data. For example, to accommodate future loads, you need to know how many additional resources (such as processor capacity, memory usage, disk capacity, or network bandwidth) are necessary to support future usage levels.
* Capacity testing helps you to identify a scaling strategy in order to determine whether you should scale up or scale out.


# Summary Matrix of Benefits by Key Performance Test Types

## Performance test
Benefits
* Determines the speed, scalability and stability characteristics of an application, thereby providing an input to making sound business decisions.
* Focuses on determining if the user of the system will be satisfied with the performance characteristics of the application.
* Identifies mismatches between performance-related expectations and reality.
* Supports tuning, capacity planning, and optimization efforts.

Challenges and Areas Not Addressed
* May not detect some functional defects that only appear under load.
* If not carefully designed and validated, may only be indicative of performance characteristics in a very small number of production scenarios.
* Unless tests are conducted on the production hardware, from the same machines the users will be using, there will always be a degree of uncertainty in the results.


## Load test
Benefits
* Determines the throughput required to support the anticipated peak production load.
* Determines the adequacy of a hardware environment.
* Evaluates the adequacy of a load balancer.
* Detects concurrency issues.
* Detects functionality errors under load.
* Collects data for scalability and capacity-planning purposes.
* Helps to determine how many users the application can handle before performance is compromised.
* Helps to determine how much load the hardware can handle before resource utilization limits are exceeded.

Challenges and Areas Not Addressed
* Is not designed to primarily focus on speed of response.
* Results should only be used for comparison with other related load tests.



## Stress test
Benefits
* Determines if data can be corrupted by overstressing the system.
* Provides an estimate of how far beyond the target load an application can go before causing failures and errors in addition to slowness.
* Allows you to establish application-monitoring triggers to warn of impending failures.
* Ensures that security vulnerabilities are not opened up by stressful conditions.
* Determines the side effects of common hardware or supporting application failures.
* Helps to determine what kinds of failures are most valuable to plan for.

Challenges and Areas Not Addressed
* Because stress tests are unrealistic by design, some stakeholders may dismiss test results.
* It is often difficult to know how much stress is worth applying.
* It is possible to cause application and/or network failures that may result in significant disruption if not isolated to the test environment.


## Capacity test
Benefits
* Provides information about how workload can be handled to meet business requirements.
* Provides actual data that capacity planners can use to validate or enhance their models and/or predictions.
* Enables you to conduct various tests to compare capacity-planning models and/or predictions.
* Determines the current usage and capacity of the existing system to aid in capacity planning.
* Provides the usage and capacity trends of the existing system to aid in capacity planning

Challenges and Areas Not Addressed
* Capacity model validation tests are complex to create.
* Not all aspects of a capacity-planning model can be validated through testing at a time when those aspects would provide the most value.


# Summary Table of Core Performance-Testing Activities

## Activity 1. Identify the Test Environment
### Input
* Logical and physical production architecture
* Logical and physical test architecture
* Available tools

### Output
* Comparison of test and production environments
* Environment-related concerns
* Determination of whether additional tools are required

## Activity 2. Identify Performance Acceptance Criteria
### Input
* Client expectations
* Risks to be mitigated
* Business requirements
* Contractual obligations
### Output
* Performance-testing success criteria
* Performance goals and requirements
* Key areas of investigation
* Key performance indicators
* Key business indicators

## Activity 3. Plan and Design Tests
### Input
* Available application features and/or components
* Application usage scenarios
* Unit tests
* Performance acceptance criteria
### Output
* Conceptual strategy
* Test execution prerequisites
* Tools and resources required
* Application usage models to be simulated
* Test data required to implement tests
* Tests ready to be implemented

## Activity 4. Configure the Test Environment
### Input
* Conceptual strategy
* Available tools
* Designed tests
### Output
* Configured load-generation and resource-monitoring tools
* Environment ready for performance testing

## Activity 5. Implement the Test Design
### Input
* Conceptual strategy
* Available tools/environment
* Available application features and/or components
* Designed tests
### Output
* Validated, executable tests
* Validated resource monitoring
* Validated data collection

## Activity 6. Execute the Test
### Input
* Task execution plan
* Available tools/environment
* Available application features and/or components
* Validated, executable tests
### Output
* Test execution results

## Activity 7. Analyze Results, Report, and Retest
### Input
* Task execution results
* Performance acceptance criteria
* Risks, concerns, and issues
### Output
* Results analysis
* Recommendations
* Reports

# Activity 1. Identify the Test Environment
The environment in which your performance tests will be executed, along with the tools and associated hardware necessary to execute the performance tests, constitute the test environment. Under ideal conditions, if the goal is to determine the performance characteristics of the application in production, the test environment is an exact replica of the production environment but with the addition of load-generation and resource-monitoring tools. Exact replicas of production environments are uncommon.

The degree of similarity between the hardware, software, and network configuration of the application under test conditions and under actual production conditions is often a significant consideration when deciding what performance tests to conduct and what size loads to test. It is important to remember that it is not only the physical and software environments that impact performance testing, but also the objectives of the test itself. Often, performance tests are applied against a proposed new hardware infrastructure to validate the supposition that the new hardware will address existing performance concerns.

The key factor in identifying your test environment is to completely understand the similarities and differences between the test and production environments. Some critical factors to consider are:

## Hardware
* Configurations
* Machine hardware (processor, RAM, etc.)

## Network
* Network architecture and end-user location
* Load-balancing implications
* Cluster and Domain Name System (DNS) configurations

## Tools
* Load-generation tool limitations
* Environmental impact of monitoring tools

## Software
* Other software installed or running in shared or virtual environments
* Software license constraints or differences
* Storage capacity and seed data volume
* Logging levels

## External factors
* Volume and type of additional traffic on the network
* Scheduled or batch processes, updates, or backups
* Interactions with other systems

## Considerations
Consider the following key points when characterizing the test environment:
* Although few performance testers install, configure, and administrate the application being tested, it is beneficial for the testers to have access to the servers and software, or to the administrators who do.
* Identify the amount and type of data the application must be seeded with to emulate real-world conditions.
Identify critical system components. Do any of the system components have known performance concerns? Are there any integration points that are beyond your control for testing?
* Get to know the IT staff. You will likely need their support to perform tasks such as monitoring overall network traffic and configuring your load-generation tool to simulate a realistic number of Internet Protocol (IP) addresses.
* Check the configuration of load balancers.
* Validate name resolution with DNS. This may account for significant latency when opening database connections.
* Validate that firewalls, DNS, routing, and so on treat the generated load similarly to a load that would typically be encountered in a production environment.
* It is often appropriate to have systems administrators set up resource-monitoring software, diagnostic tools, and other utilities in the test environment.

# Activity 2. Identify Performance Acceptance Criteria
It generally makes sense to start identifying, or at least estimating, the desired performance characteristics of the application early in the development life cycle. This can be accomplished most simply by noting the performance characteristics that your users and stakeholders equate with good performance. The notes can be quantified at a later time.

Classes of characteristics that frequently correlate to a user’s or stakeholder’s satisfaction typically include:
* **Response time.** For example, the product catalog must be displayed in less than three seconds.
* **Throughput.** For example, the system must support 25 book orders per second.
* **Resource utilization.** For example, processor utilization is not more than 75 percent. Other important resources that need to be considered for setting objectives are memory, disk input/output (I/O), and network I/O.

## Considerations
Consider the following key points when identifying performance criteria:
* Business requirements
* User expectations
* Contractual obligations
* Regulatory compliance criteria and industry standards
* Service Level Agreements (SLAs)
* Resource utilization targets
* Various and diverse, realistic workload models
* The entire range of anticipated load conditions
* Conditions of system stress
* Entire scenarios and component activities
* Key performance indicators
* Previous releases of the application
* Competitor’s applications
* Optimization objectives
* Safety factors, room for growth, and scalability
* Schedule, staffing, budget, resources, and other priorities
 
# Activity 3. Plan and Design Tests
Planning and designing performance tests involves identifying key usage scenarios, determining appropriate variability across users, identifying and generating test data, and specifying the metrics to be collected. Ultimately, these items will provide the foundation for workloads and workload profiles.

When designing and planning tests with the intention of characterizing production performance, your goal should be to create real-world simulations in order to provide reliable data that will enable your organization to make informed business decisions. Real-world test designs will significantly increase the relevancy and usefulness of results data.

Key usage scenarios for the application typically surface during the process of identifying the desired performance characteristics of the application. If this is not the case for your test project, you will need to explicitly determine the usage scenarios that are the most valuable to script. Consider the following when identifying key usage scenarios:

Contractually obligated usage scenario(s)
* Usage scenarios implied or mandated by performance-testing goals and objectives
* Most common usage scenario(s)
* Business-critical usage scenario(s)
* Performance-intensive usage scenario(s)
* Usage scenarios of technical concern
* Usage scenarios of stakeholder concern
* High-visibility usage scenarios

When identified, captured, and reported correctly, metrics provide information about how your application’s performance compares to your desired performance characteristics. In addition, metrics can help you identify problem areas and bottlenecks within your application.

It is useful to identify the metrics related to the performance acceptance criteria during test design so that the method of collecting those metrics can be integrated into the tests when implementing the test design. When identifying metrics, use either specific desired characteristics or indicators that are directly or indirectly related to those characteristics.

## Considerations
* Consider the following key points when planning and designing tests:
* Realistic test designs are sensitive to dependencies outside the control of the system, such as humans, network activity, and other systems interacting with the application.
* Realistic test designs are based on what you expect to find in real-world use, not theories or projections.
* Realistic test designs produce more credible results and thus enhance the value of performance testing.
* Component-level performance tests are integral parts of realistic testing.
* Realistic test designs can be more costly and time-consuming to implement, but they provide far more accuracy for the business and stakeholders.
* Extrapolating performance results from unrealistic tests can create damaging inaccuracies as the system scope increases, and frequently lead to poor decisions.
* Involve the developers and administrators in the process of determining which metrics are likely to add value and which method best integrates the capturing of those metrics into the test.
* Beware of allowing your tools to influence your test design. Better tests almost always result from designing tests on the assumption that they can be executed and then adapting the test or the tool when that assumption is proven false, rather than by not designing particular tests based on the assumption that you do not have access to a tool to execute the test.

Realistic test designs include:
* Realistic simulations of user delays and think times, which are crucial to the accuracy of the test.
* User abandonment, if users are likely to abandon a task for any reason.
* Common user errors.

# Activity 4. Configure the Test Environment
Preparing the test environment, tools, and resources for test design implementation and test execution prior to features and components becoming available for test can significantly increase the amount of testing that can be accomplished during the time those features and components are available.

Load-generation and application-monitoring tools are almost never as easy to get up and running as one expects. Whether issues arise from setting up isolated network environments, procuring hardware, coordinating a dedicated bank of IP addresses for IP spoofing, or version compatibility between monitoring software and server operating systems, issues always seem to arise from somewhere. Start early, to ensure that issues are resolved before you begin testing.

Additionally, plan to periodically reconfigure, update, add to, or otherwise enhance your load-generation environment and associated tools throughout the project. Even if the application under test stays the same and the load-generation tool is working properly, it is likely that the metrics you want to collect will change. This frequently implies some degree of change to, or addition of, monitoring tools.

## Considerations
* Consider the following key points when configuring the test environment:
* Determine how much load you can generate before the load generators reach a bottleneck. Typically, load generators encounter bottlenecks first in memory and then in the processor.
* Although it may seem like a commonsense practice, it is important to verify that system clocks are synchronized on all of the machines from which resource data will be collected. * Doing so can save you significant time and prevent you from having to dispose of the data entirely and repeat the tests after synchronizing the system clocks.
* Validate the accuracy of load test execution against hardware components such as switches and network cards. For example, ensure the correct full-duplex mode operation and correct * emulation of user latency and bandwidth.
* Validate the accuracy of load test execution related to server clusters in load-balanced configuration. Consider using load-testing techniques to avoid affinity of clients to servers due to their using the same IP address. Most load-generation tools offer the ability to simulate usage of different IP addresses across load-test generators.
* Monitor resource utilization (CPU, network, memory, disk and transactions per time) across servers in the load-balanced configuration during a load test to validate that the load is distributed.

# Activity 5. Implement the Test Design
The details of creating an executable performance test are extremely tool-specific. Regardless of the tool that you are using, creating a performance test typically involves scripting a single usage scenario and then enhancing that scenario and combining it with other scenarios to ultimately represent a complete workload model.

Load-generation tools inevitably lag behind evolving technologies and practices. Tool creators can only build in support for the most prominent technologies and, even then, these have to become prominent before the support can be built. This often means that the biggest challenge involved in a performance-testing project is getting your first relatively realistic test implemented with users generally being simulated in such a way that the application under test cannot legitimately tell the difference between the simulated users and real users. Plan for this and do not be surprised when it takes significantly longer than expected to get it all working smoothly.

## Considerations
Consider the following key points when implementing the test design:
* Ensure that test data feeds are implemented correctly. Test data feeds are data repositories in the form of databases, text files, in-memory variables, or spreadsheets that are used to simulate parameter replacement during a load test. For example, even if the application database test repository contains the full production set, your load test might only need to simulate a subset of products being bought by users due to a scenario involving, for example, a new product or marketing campaign. Test data feeds may be a subset of production data repositories.
* Ensure that application data feeds are implemented correctly in the database and other application components. Application data feeds are data repositories, such as product or order databases, that are consumed by the application being tested. The key user scenarios, run by the load test scripts may consume a subset of this data.
* Ensure that validation of transactions is implemented correctly. Many transactions are reported successful by the Web server, but they fail to complete correctly. Examples of * validation are, database entries inserted with correct number of rows, product information being returned, correct content returned in html data to the clients etc.
* Ensure hidden fields or other special data are handled correctly. This refers to data returned by Web server that needs to be resubmitted in subsequent request, like session IDs or product ID that needs to be incremented before passing it to the next request.
* Validate the monitoring of key performance indicators (KPIs).
* Add pertinent indicators to facilitate articulating business performance.
* If the request accepts parameters, ensure that the parameter data is populated properly with variables and/or unique data to avoid any server-side caching.
* If the tool does not do so automatically, consider adding a wrapper around the requests in the test script in order to measure the request response time.
* It is generally worth taking the time to make the script match your designed test, rather than changing the designed test to save scripting time.
* Significant value can be gained from evaluating the output data collected from executed tests against expectations in order to test or validate script development.

#Activity 6. Execute the Test
Executing tests is what most people envision when they think about performance testing. It makes sense that the process, flow, and technical details of test execution are extremely dependent on your tools, environment, and project context. Even so, there are some fairly universal tasks and considerations that need to be kept in mind when executing tests.

Much of the performance testing–related training available today treats test execution as little more than starting a test and monitoring it to ensure that the test appears to be running as expected. In reality, this activity is significantly more complex than just clicking a button and monitoring machines.

Test execution can be viewed as a combination of the following sub-tasks:
* Coordinate test execution and monitoring with the team.
* Validate tests, configurations, and the state of the environments and data.
* Begin test execution.
* While the test is running, monitor and validate scripts, systems, and data.
* Upon test completion, quickly review the results for obvious indications that the test was flawed.
* Archive the tests, test data, results, and other information necessary to repeat the test later if needed.
* Log start and end times, the name of the result data, and so on. This will allow you to identify your data sequentially after your test is done.

As you prepare to begin test execution, it is worth taking the time to double-check the following items:
* Validate that the test environment matches the configuration that you were expecting and/or designed your test for.
* Ensure that both the test and the test environment are correctly configured for metrics collection.
* Before running the real test, execute a quick smoke test to make sure that the test script and remote performance counters are working correctly. In the context of performance * testing, a smoke test is designed to determine if your application can successfully perform all of its operations under a normal load condition for a short time.
* Reset the system (unless your scenario calls for doing otherwise) and start a formal test execution.
* Make sure that the test scripts’ execution represents the workload model you want to simulate.
* Make sure that the test is configured to collect the key performance and business indicators of interest at this time.

## Considerations
* Consider the following key points when executing the test:
* Validate test executions for data updates, such as orders in the database that have been completed.
* Validate if the load-test script is using the correct data values, such as product and order identifiers, in order to realistically simulate the business scenario.
* Whenever possible, limit test execution cycles to one to two days each. Review and reprioritize after each cycle.
* If at all possible, execute every test three times. Note that the results of first-time tests can be affected by loading Dynamic-Link Libraries (DLLs), populating server-side * caches, or initializing scripts and other resources required by the code under test. If the results of the second and third iterations are not highly similar, execute the test again. Try to determine what factors account for the difference.
* Observe your test during execution and pay close attention to any behavior you feel is unusual. Your instincts are usually right, or at least valuable indicators.
* No matter how far in advance a test is scheduled, give the team 30-minute and 5-minute warnings before launching the test (or starting the day’s testing) if you are using a shared test environment. Additionally, inform the team whenever you are not going to be executing for more than one hour in succession so that you do not impede the completion of their tasks.
* Do not process data, write reports, or draw diagrams on your load-generating machine while generating a load, because this can skew the results of your test.
* Turn off any active virus-scanning on load-generating machines during testing to minimize the likelihood of unintentionally skewing the results of your test.
* While load is being generated, access the system manually from a machine outside of the load-generation environment during test execution so that you can compare your observations with the results data at a later time.
* Remember to simulate ramp-up and cool-down periods appropriately.
* Do not throw away the first iteration because of application script compilation, Web server cache building, or other similar reasons. Instead, measure this iteration separately so that you will know what the first user after a system-wide reboot can expect.
* Test execution is never really finished, but eventually you will reach a point of diminishing returns on a particular test. When you stop obtaining valuable information, move on to other tests.
* If you feel you are not making progress in understanding an observed issue, it may be more efficient to eliminate one or more variables or potential causes and then run the test again.

# Activity 7. Analyze Results, Report, and Retest
Managers and stakeholders need more than just the results from various tests — they need conclusions, as well as consolidated data that supports those conclusions. Technical team members also need more than just results — they need analysis, comparisons, and details behind how the results were obtained. Team members of all types get value from performance results being shared more frequently.

Before results can be reported, the data must be analyzed. Consider the following important points when analyzing the data returned by your performance test:
* Analyze the data both individually and as part of a collaborative, cross-functional technical team.
* Analyze the captured data and compare the results against the metric’s acceptable or expected level to determine whether the performance of the application being tested shows a trend toward or away from the performance objectives.
* If the test fails, a diagnosis and tuning activity are generally warranted.
* If you fix any bottlenecks, repeat the test to validate the fix.
* Performance-testing results will often enable the team to analyze components at a deep level and correlate the information back to the real world with proper test design and usage analysis.
* Performance test results should enable informed architecture and business decisions.
* Frequently, the analysis will reveal that, in order to completely understand the results of a particular test, additional metrics will need to be captured during subsequent test-execution cycles.
* Immediately share test results and make raw data available to your entire team.
* Talk to the consumers of the data to validate that the test achieved the desired results and that the data means what you think it means.
* Modify the test to get new, better, or different information if the results do not represent what the test was defined to determine.
* Use current results to set priorities for the next test.
* Collecting metrics frequently produces very large volumes of data. Although it is tempting to reduce the amount of data, always exercise caution when using data-reduction techniques because valuable data can be lost.
* Most reports fall into one of the following two categories:

Technical Reports
* Description of the test, including workload model and test environment.
* Easily digestible data with minimal pre-processing.
* Access to the complete data set and test conditions.
* Short statements of observations, concerns, questions, and requests for collaboration.

Stakeholder Reports
* Criteria to which the results relate.
* Intuitive, visual representations of the most relevant data.
* Brief verbal summaries of the chart or graph in terms of criteria.
* Intuitive, visual representations of the workload model and test environment.
* Access to associated technical reports, complete data sets, and test conditions.
* Summaries of observations, concerns, and recommendations.

The key to effective reporting is to present information of interest to the intended audience in a manner that is quick, simple, and intuitive. The following are some underlying principles for achieving effective reports:
* Report early, report often.
* Report visually.
* Report intuitively.
* Use the right statistics.
* Consolidate data correctly.
* Summarize data effectively.
* Customize for the intended audience.
* Use concise verbal summaries using strong but factual language.
* Make the data available to stakeholders.
* Filter out any unnecessary data.
* If reporting intermediate results, include the priorities, concerns, and blocks for the next several test-execution cycles.


# Modeling Performance Tests
https://docs.microsoft.com/en-us/previous-versions/msp-n-p/bb924367(v=pandp.10)
https://www.neotys.com/blog/modeling-performance-tests/
https://techbeacon.com/how-define-right-workload-model-your-performance-tests
https://dzone.com/articles/modeling-performance-tests
http://www.agileload.com/agileload/blog/2013/06/12/performance-test-workload-modeling
https://smartbear.com/blog/test-and-monitor/workload-modeling-and-profiles-for-load-testing/
https://www.cs.auckland.ac.nz/~christof/publications/LutterothWeber2008-LoadTesting.pdf

![1](https://qph.fs.quoracdn.net/main-qimg-7d320fdbfe44f5ef1c1b7ef974bdc988.webp)

Considerations while designing Workload Model :

* Some users will complete more than one activity during a visit to your site.
* Some users will complete the same activity more than once per visit.
* Some users may not actually complete any activities during a visit to your site.
* Navigation paths are often easiest to capture by using page titles.
* If page titles do not work or are not intuitive for your application, the navigation path may be easily defined by steps the user takes to complete the activity.
* First-time users frequently follow a different path to accomplish a task than users experienced with the application. Consider this difference and what percentage of new versus return user navigation paths you should represent in your model.
* Different users will spend different amounts of time on the site. Some will log out, some will close their browser, and others will leave their session to time out. Take these factors into account when determining or estimating session durations.
* When discussing navigation paths with your team or others, it is frequently valuable to use visual representations.


# Statergy

1. Determine the Scope of Testing/Nonfunctional Requirements: This includes basic check on what all requirements are agreed upon under what deadlines, Resources,Identified performance targets, tools, skills, and appropriate licenses for the performance test(if required). Adequate training for all team members in the tools to be used.
 
 2. Performance Test Environment Build: Take into account the load models(server monitoring/load test) and deploying,configuring performance testing tools correctly so that build/env is ready to work since we strive to make test environment as close as that of production Test Page for the Apache HTTP Server & InterWorx-CP also involves identifying acceptance criteria.
 
 3. Scripting/Use-Case Scripting: Now once above 2 things are handles,here comes in major approach/line item to be followed i.e scripting of all the business scenarios,for which following steps will be required:
 a. Identifying the sessions data requirement and then Confirm and apply input data.
 b. Checkpoint coverage at appropriate places which provides first-level analysis of potential problem areas within the use case.
 c. Identify the changes required and apply them in use cases so as to get correct results/output.[Note: Use cases should work correctly in both cases whether for Single or Multi-user ]
 
 4. Performance Test Scenario Build: It includes making use of the load model created which was captured as part of NFR/scope defining approach.Focus is on below areas:
 a. Type of test to be run: Whether pipe-clean, Spike,Volume,Soak, or Stress? Mostly, we use pipe-clean tests for each use case initially as a single user to establish a performance baseline, and then target throughput for the use case.
 b. For each use case, decision on how many load injector deployments are required and virtual users to be assigned to each point of presence
 c. Put required think time and pacing as business flow demands
 
 5. Performance Test Execution and Analysis: Last and the important approach is to Run and monitor test results. Final check/dress rehearsals are performed so that there are no problems accessing the application or with the test configuration.
 a. Ensuring that we haven’t omitted anything fundamental in performance test configuration.
 b. Execute volume tests once performance baselines are established.
 c. Execute isolation tests to explore any problems revealed by volume testing and stress tests, which are crucial from a capacity perspective.
 
 6. Post-Test Analysis and Reporting: Final and important step is after running/executing ,make sure to have clean and precise analysis of the task and the best way is to prepare the reports after each run performed and a closure report for same.
 a. Determine success or failure by comparing test results to performance targets set as part of project requirements.
 b. Document the results using your preferred reporting template
 c. A closure report containing Key business scenario,Scopes,Bottlenecks Identified(database configuration, coding errors, hardware issues etc) and vulnerable areas being identified shall prove good.
 A conclusion with recommendation ideas is always treated good & interactive way to Report.
 
 
 At a minimum, a performance testing plan needs to address the following:

Overall approach
Focus on mitigating the performance risks for this new implementation.
Make basic working assumptions on which parts of the implementation need to be performance-tested.
Reach consensus on these working assumptions and determine the appropriate level of performance and stress testing that shall be completed within this compressed time schedule.
Dependencies and baseline assumptions
Components to be performance tested shall be completely functional.
Components to be performance tested shall be housed in hardware/firmware components that are representative or scaleable to the intended production systems.
Data repositories shall be representative or scaleable to the intended production systems.
Performance objectives shall be agreed upon, including working assumptions and testing scenarios.
Performance testing tools and supporting technologies shall be installed and fully licensed.
Pre-performance testing actions
Create a "stubs" or "utilities" to push transactions through the QA environment -– using projected peak loads.
Create a "stubs" or "utilities" to replace business-to-business transactions that are not going to be tested or will undergo limited performance. This would remove any dependencies on B2B transactions.
Create a "stubs" or "utilities" to replace internal components that will not be available during performance testing. This would remove any dependencies on these components.
Implement appropriate performance monitors on all high-volume servers.
Performance testing approach
Focus on mitigating the performance risks for this new implementation.
Make basic working assumptions on which parts of the implementation need to be performance-tested.
Reach consensus on these working assumptions and determine the appropriate level of performance that shall be completed.
Use a tier 1 performance testing tool that can replicate the expected production volumes.
Use an environment that replicates the components (as they will exist in production) that will be performance-tested -– noting all exceptions.
Use both production and non-production (testing) monitors to measure the performance of the system during performance testing.
Performance testing activities
Performance test shall create appropriate loads against the system following agreed-upon scenarios that include:User actions (workflow)Agreed-upon loads (transactions per minute)Agreed-upon metrics (response times)
Manual testing and automated functional tests shall be conducted during performance testing to ensure that user activities are not impacted by the current load.
System monitors shall be used to observe the performance of all servers involved in the test to ensure they meet predefined performance requirements.
Post-implementation support teams shall be represented during performance testing to observe and support the performance testing efforts.
In-scope business processes
Out-of-scope business processes
Performance testing scenarios
Business scenario
Expected throughput (peak)
Acceptance performance criteria (acceptable response times under various loads)
Data requirements (scenario and implementation specific)
Performance test execution
Performance test metrics
In-short a good approach organises "CCD IS EARI" into a flow that fits your project

Context - the overall vision or intent of the project, performance testing objectives, performance success criteria, the development life cycle, the project schedule, the project budget, the available tools and environments, the skill set of the performance tester and the team, the priority of detected performance concerns, and the business impact of deploying an application that performs poorly

Criteria - criteria include requirements, goals, targets, thresholds and objectives related to both the application's performance and the performance testing sub-project

Design - A significant component of performance test design is determining, designing and creating data associated with the natural variances of application users

Install - This heuristic is actually short for "Install and Configure or Update Tools and the Load Generation Environment

Script - It is most likely that your test design will be implemented using a load generation tool that requires some degree of scripting.

Execute - The fact is that test execution involves continually validating the tests and test environment, running new tests and archiving all of the data associated with test execution.

Analyse - Analysing test results and collected data, whether to determine requirement compliance, track trends, detect bottlenecks or evaluate the effectiveness of tuning efforts, is crucial to the success of a performance testing project

Report - Reporting on the results and analysis is just as significant as the collection and analysis of the data

Iterate - Iterating is virtually a given for any type of testing. Sometimes we iterate based on builds, defect resolutions or environment changes.


# Coordinating Performance Testing with an Iteration-Based Process

Iterative Performance Testing Activities
This approach can be represented by using the following nine activities:
Iterative Performance Testing Activities

Activity 1. Understand the Project Vision and Context. The outcome of this activity is a shared understanding of the project vision and context.
Activity 2. Identify Reasons for Testing Performance. Explicitly identify the reasons for performance testing.
Activity 3. Identify the Value Performance Testing Adds to the Project. Translate the project- and business-level objectives into specific, identifiable, and manageable performance-testing activities.
Activity 4. Configure the Test Environment. Set up the load-generation tools and the system under test, collectively known as the performance test environment.
Activity 5. Identify and Coordinate Tasks. Prioritize and coordinate support, resources, and schedules to make the tasks efficient and successful.
Activity 6. Execute Task(s). Execute the activities for the current iteration.
Activity 7. Analyze Results and Report. Analyze and share results with the team.
Activity 8. Revisit Activities 1-3 and Consider Performance Acceptance Criteria. Between iterations, ensure that the foundational information has not changed. Integrate new information such as customer feedback and update the strategy as necessary.
Activity 9. Reprioritize Tasks. Based on the test results, new information, and the availability of features and components, reprioritize, add to, or delete tasks from the strategy, and then return to activity 5.

![1](https://docs.microsoft.com/en-us/previous-versions/msp-n-p/images/bb924360.image001%28en-us%2cpandp.10%29.gif)
![2](https://docs.microsoft.com/en-us/previous-versions/msp-n-p/images/bb924360.image002%28en-us%2cpandp.10%29.gif)


## Activity 1. Understand the Project Vision and Context
The project vision and context are the foundation for determining what performance testing activities are necessary and valuable. Because the performance tester is not driving these items, the coordination aspect refers more to team education about the performance implications of the project vision and context, and to identifying areas where future coordination will likely be needed for success.

A critical part of working with an iteration-based process is asking the correct questions, providing the correct value, and performing the correct task related to each step. Although situations can shift or add more questions, values, or tasks, a sample checklist is provided as a starting point for each step.

### Checklist
Questions to ask:
* What are the performance implications of the project vision?
* What are the performance implications of the service the application is intended to provide, or what problem are we trying to solve for the customer?
* How does the team envision performance testing as it relates to the project schedule, structure, and available resources?

### Value provided:
* Be involved in the product concept.
* Point out any areas of concern immediately.
* Point out assumptions related to available resources, tools, and resource-monitoring instrumentation based on the project vision and context as soon as they arise.

### Tasks accomplished:
* Ask the whole team questions and provide answers.
* Determine the team’s perception of performance testing.
* Gain a conceptual understanding of the project’s critical performance implications.
* Begin to define equipment and/or resources needed for conducting performance testing.
* Understand resource constrains; for example, budget, people, equipment.
* Understand how the team will coordinate.
* Understand how the team will communicate.

Coordinate with:
* Whole team

## Activity 2. Identify Reasons for Testing Performance
The underlying reasons for testing performance on a particular project are not always obvious based on the vision and context alone. Project teams generally do not include performance testing as part of the project unless there is some performance-related risk or concern they feel needs to be mitigated. Explicitly identifying these risks and areas of concern is the next fundamental step in determining what specific performance testing activities will add the most value to the project.

Having a full-time performance tester on the team from the start of the project may frequently be a good idea, but it does not happen frequently. Generally, when a performance tester is present at project inception, it means there is a specific, significant risk that the tester is there to address.

Regardless of when a performance tester joins the team, once the project vision and context are understood, it is worth taking the time to verbalize and/or document the overall objectives of the performance-testing effort based on the risks or concerns that the team has. The following checklist should help you to accomplish this step.

### Checklist
Questions to ask:
* What risk(s) is performance testing intended to mitigate for this project?
* Are there specific contractual, compliance, or customer performance expectations that are already known to be required?
* What performance concerns relating to this project already exist?

### Value provided:
* Be involved in the product concept.
* Point out any areas of concern immediately.
* Point out resource and instrumentation assumptions based on the project vision and context when they arise.
* Guide the process of collecting/determining performance-testing objectives.
* Capture implied usage scenarios of particular performance concerns.
* Capture implied performance goals, requirements, targets, and thresholds as they come up in conversation.

### Tasks accomplished:
* Ask the whole team questions and provide answers.
* Determine the project-level objectives for conducting performance testing.
* Refine estimates of equipment and/or resources required for conducting performance testing.
* Identify disconnects between the objectives of the performance-testing effort and the equipment and resources to be made available.
* Capture implied performance goals, requirements, targets, and thresholds to be fleshed out later.
* Capture implied usage scenarios of particular concern to be fleshed out later.

### Coordinate with:
* Whole team

## Activity 3. Identify the Value Performance Testing Adds to the Project
Using information gained from activities 1 and 2, you can now clarify the value added through performance testing, and convert that value into a conceptual performance-testing strategy. The point is to translate the project- and business-level objectives into specific, identifiable, and manageable performance-testing activities. The coordination aspect of this step involves team-wide discussion and agreement on which performance-testing activities are likely to add value or provide valuable information, and if these activities are worth planning for at this time.

### Checklist
Questions to ask:
* What performance-testing activities will help achieve the performance-testing objectives?
* What performance-testing activities are needed to validate any contractual, compliance, project, or customer performance criteria or expectations that are known at this time?
* What performance-testing activities will help address currently known performance concerns?

### Value provided:
* Ensure team-wide support of performance-testing activities.
* Ensure that the team has adequate warning about performance-testing activities that will require the support of additional team members.
* Determine if resource and instrumentation assumptions are adequate.
* Guide the process of determining how performance-testing objectives will be measured.
* Capture additional implied usage scenarios of particular performance concerns.
* Capture additional implied performance goals, requirements, targets, and thresholds as they come up in conversation.

### Tasks accomplished:
* Ask the whole team questions and provide answers.
* Determine a conceptual project-level strategy for determining if the objectives for conducting performance testing have been met.
* Refine estimates of equipment and/or resources required for conducting performance testing.
* Identify disconnects between the objectives of the performance-testing effort and the equipment and resources to be made available.
* Capture additional implied performance goals, requirements, targets, and thresholds to be fleshed out later.
* Capture additional implied usage scenarios of particular concern to be fleshed out later.

### Coordinate with:
* Whole team

## Activity 4. Configure the Test Environment
With a conceptual strategy in place, prepare the tools and resources in order to execute the strategy as features and components become available for test. Take this step as soon as possible, so that the team has this resource from the beginning.

This step is fairly straightforward. Set up the load-generation tools and the system under test — collectively known as the performance test environment — and ensure that this environment will meet engineering needs. The coordination component of this step typically involves asking managers and administrators to obtain and/or configure equipment and other resources that are not under the direct control of the team or performance tester.

### Checklist
Questions to ask:
* Who administrates the performance-testing environment of the application under test?
* Who administrates the load-generation tool/environment?
* Who configures and operates resource monitors for the application under test?
* Is special permission needed prior to generating load of a certain volume?
* Who can reset the application under test?
* What other components require special coordination?
* What security or authentication considerations are there for simulating multiple users?
* What coordination needs to be done to enable the use of recording and/or monitoring software?

### Value provided:
* Ensure that the load-generation and performance-test environments are ready when the team needs them.
* Ensure that the entire team knows who to contact for help with performance-testing environment support.
* Ensure that performance testing support staff knows what they are supporting.

### Tasks accomplished:
* Performance-test environment configured and ready to begin testing.
* Load-generation environment configured and ready to begin testing.
* Support responsibilities assigned.
* Special permissions, time of day for high load tests, etc., determined.

### Coordinate with:
* System administrators
* Network support
* Database administrators
* Infrastructure support
* Managers of those above
* Development team

## Activity 5. Identify and Coordinate Tasks
Performance testing tasks do not happen in isolation. The performance specialist needs to work with the team to prioritize and coordinate support, resources, and schedules to make the tasks efficient and successful.

During the pre-iteration planning meeting, look at where the project is now and where you want to be to determine what should and can be done next. When planning for the iteration cycle, the performance tester is driven by the goals that have been determined for this cycle. This step also includes signing up for the activities that will be accomplished during this cycle.

### Checklist
Questions to ask:
* What is the performance goal for this cycle?
* Where is the project in terms of the overall project performance goals?
* Has the system achieved all of its performance objectives?
* Has tuning been accomplished since the last iteration?
* What analysis, reports, or retesting will add value during this iteration?
* Who requires pairing in order to do performance testing?
* How much time is available?
* How much time does each task take?
* What is the most critical activity?

### Value provided:
* Provide insight on how the overall project is achieving its goal.
* Provide insight on what can be measured and reported on in this cycle.
* Provide insight on any critical issues that may have arisen from the last iteration cycle.
* Make suggestions to other team members.
* Transfer lessons learned as they emerge from the test.
* Pair with developers to improve performance unit testing.
* Help reuse unit tests.
* Help reuse functional tests.

### Tasks accomplished:
* Estimate how much work is achievable.
* Determine if anyone needs to be paired out.
* Prioritize achievable work.
* Identify primary and alternate tasks for this cycle.

### Coordinate with:
* Managers and stakeholders
* Developers and administrators
* Infrastructure and test environment support
* Users or user representatives

## Activity 6. Execute Task(s)
Conduct tasks in one- to two-day segments. See them through to completion, but be willing to take important detours along the way if an opportunity to add additional value presents itself. Step 5 defines what work the team members will sign up for in this iteration. Now it is time to execute the activities for this iteration.

### Checklist
Questions to ask:
* Have recent test results or project updates made this task more or less valuable compared to other tests we could be conducting right now?
* What additional team members should be involved with this task?
* Are there other important tasks that can be conducted in parallel with this one?
* Do the preliminary results make sense?
* Is the test providing the data we expected?

### Value provided:
* Evaluate algorithm efficiency.
* Monitor resource usage trends.
* Measure response times.
* Collect data for scalability and capacity planning.
* Transfer lessons learned as they emerge from the test.
* Improve performance unit testing by pairing performance testers with developers.
* Help reuse unit tests.
* Help reuse functional tests.

### Tasks accomplished:
* Conduct tests.
* Collect data.
* Validate test assumptions and techniques.
* Potentially tune while testing.
* Pair with other team members; this does not mean only working with a developer or tester but can also mean working with a writer to capture his or her understanding of how the * system performance works, or working with the customer directly.

### Coordinate with:
* Developers and administrators
* Infrastructure and test environment support
* Users or user representatives
* Managers and stakeholders
* Other performance testers who are not on the project

# Activity 7. Analyze Results and Report
To keep up with an iterative process, results need to be analyzed and shared quickly. If the analysis is inconclusive, retest at the earliest possible opportunity to give the team maximum time to react to performance issues. As the project is wrapped for final shipping, it is usually worth having a meeting afterward to collect and pass along lessons learned. In most cases it is valuable to have a daily or every-other-day update to share information and coordinate next tasks.

### Checklist
Questions to ask:
* Do the preliminary results make sense?
* Is the test providing the data we expected?
* Is the data valuable?
* Are more tests required to derive meaning from the data?
* Is tuning required? If so, do we know what to tune?
* Do the results indicate that there are additional tests that we need to execute that have not been planned for?
* Do the results indicate that any of the tests we are planning to conduct are no longer necessary?
* Have any performance objectives been met?
* Have any performance objectives been rendered obsolete?

### Value provided:
* Evaluate algorithm efficiency.
* Monitor resource usage trends.
* Measure response times.
* Collect data for scalability and capacity planning.
* Transfer lessons learned as they emerge from the test.

### Tasks accomplished:
* Analyze data collaboratively.
* Determine the meaning of the results.
* Share data with the whole team.
* Import lessons learned into future iteration planning.

### Coordinate with:
* Developers and administrators
* Managers and stakeholders
* Users or user representatives
* Other performance testers who are not on the project

## Activity 8. Revisit Activities 1-3 and Consider Performance Acceptance Criteria
Between iterations, ensure that the foundational information has not changed. Integrate new information, such as customer feedback, and update the strategy as necessary.

### Checklist
Questions to ask:
* Have the performance implications of the project vision changed?
* Have the performance implications of the service we are trying to provide changed, or has the problem we are trying to solve for the customer changed?
* Have the project schedule, structure, or available resources changed?
* Have the performance-testing objectives changed?
* Have the performance-testing activities needed to validate any contractual, compliance, project, or customer performance criteria or expectations changed?
* What performance-testing activities will help address currently known performance concerns?

### Value provided:
* Update resource and instrumentation assumptions and needs.
* Point out any areas of concern.
* Point out resource and instrumentation needs and/or risks.
* Update performance-testing objectives.
* Enhance and update usage scenarios of particular performance concerns.
* Enhance and update performance goals, requirements, targets, and thresholds.
* Ensure that the team has adequate warning about upcoming performance-testing activities that will require the support of additional team members.

### Tasks accomplished:
* Enhance and update understanding of the project’s critical performance implications.
* Update resource constraints; for example, budget, people, and equipment.
* Update/improve how the team will coordinate.
* Update/improve how the team will communicate.
* Revise performance-testing strategy.
* Refine estimates of equipment and/or resources required for conducting performance testing.
* Identify incompatibilities or conflicts between the objectives of the performance-testing effort and the equipment and resources to be made available.
* Capture additional performance goals, requirements, targets, and thresholds.
* Capture additional usage scenarios of particular concern.
* Report current performance-testing status.

### Coordinate with:
* Whole team

## Activity 9. Reprioritize Tasks
Based on the test results, new information, and the availability of features and components, reprioritize, add to, or delete tasks from the strategy, and then return to activity 5.

### Checklist
Questions to ask:
* What performance-testing activities will help address currently known performance concerns?
* What is the performance goal for this cycle?
* Where is the project in terms of the overall project performance goals?
* Has the system achieved all of its performance objectives?
* Has tuning been accomplished since the last iteration?
* What analysis, reports, or retesting will add value during this iteration cycle?
* Who requires pairing to do performance testing?
* How much time is available?
* How much time does each task take?
* What is the most critical activity?

### Value provided:
* Provide insight on how the overall project is achieving its goal.
* Provide insight on what can be measured and reported on in this cycle.
* Provide insight on any critical issues that may have arisen from the last iteration.
* Make suggestions to other team members.
* Transfer lessons learned as they emerge from the test.
* Pair with developers to improve performance unit testing.
* Help reuse unit tests.
* Help reuse functional tests.

### Tasks accomplished:
* Report current performance-testing status.
* Estimate how much work is achievable.
* Determine if anyone needs to be paired out.
* Prioritize achievable work.
* Identify primary and alternate tasks for this cycle.

### Coordinate with:
* Managers and stakeholders
* Developers and administrators
* Infrastructure and test environment support
* Users or user representatives



# Performance Testing Strategy
https://www.360logica.com/blog/mobile-app-performance-testing-strategy/


Cloud Performance Testing: How to Build an Effective Strategy?

http://bento.cdn.pbs.org/hostedbento-qa/filer_public/smoke/load_testing.pdf


Technical Skills of a Performance Test Engineer
https://dzone.com/articles/technical-skills-of-performance-test-engineer

# Load Testing Strategy
1. Baseline Profile
2. Peak Profile
3. Stress Profile
4. Soak Profile
https://www.soapui.org/learn/load-testing/load-testing-strategies-apis.html


API Load Testing
Mobile Load Testing
Web Load Testing

http://www.performance-workshop.org/documents/Perf_Testing_Strategy_Collard.pdf

http://www.perftestplus.com/resources/Performance_Engineering_Strategy_Template.pdf



https://www.akamai.com/us/en/multimedia/documents/white-paper/the-complete-guide-to-performance-testing-your-retail-websites-and-apps.pdf

https://smartbear.com/blog/test-and-monitor/7-types-of-web-performance-tests-and-how-they-fit/

Measuring Performance With Gatling
https://dzone.com/articles/let-measure-performance-with-gatling


![1](https://dzone.com/storage/temp/10719722-types-of-performance-testing.png)

Top 10 Open Source Performance Testing Tools
https://www.testingexcellence.com/top-10-open-source-performance-testing-tools/

https://docs.microsoft.com/en-us/vsts/test/load-test/overview?view=vsts

Performance Testing Guidance for Web Applications
https://docs.microsoft.com/en-us/previous-versions/msp-n-p/bb924375(v=pandp.10)


https://dzone.com/articles/jmeter-how-to-distribute-user-load-in-the-test-pla




https://www.techwell.com/techwell-insights/2018/11/new-approach-load-testing-browser-level-users


http://www.guidanceshare.com/wiki/Chapter_3_%E2%80%93_Risks_Addressed_Through_Performance_Testing

https://www.safaribooksonline.com/library/view/performance-testing-guidance/9780735625709/ch03s04.html

(Must Read)[https://www.slideshare.net/jvenet/performance-testing-overview-75018229]
https://www.slideshare.net/SpringCentral/performance-testing-crashcourse
https://www.slideshare.net/atulpant20/jmeter-performance-testing


* 57% of users will abandon a site after 3 seconds if it doesn’t load -Kissmetrics
* The average large US corporation experiences 87 hours of network downtime a year -Gartner



According to Microsoft, the Core Performance Testing Activities are:

1. **Identify Test Environment** – where it is important to have the exact replica of the production environment
2. **Identify Performance Acceptance Criteria** – predefine the benchmarks of expected performance
3. **Plan and Design Tests** – Identification of user test scenarios based on their importance, frequency and performance impact
4. **Configure Test Environment** – setting up the test environment as in the first step
5. **Implement Test Design** – scripting user scenarios with the help of performance testing tools
6. **Execute Tests** – testing on scripted user scenarios against different user sets with different configurations
7. **Analyze, Report and Retest** – Analyze test results with benchmarks, report results to stakeholders and Re-test if necessary


# PERFORMANCE TESTING PROCESS
* COLLECT
  * Assess Business Requirements
  * Review Application Features
  * Identify Key Elements to Setup Test Environment
* PLAN & STRATEGIZE
  * Identify Performance Test Matrices
  * Define Baseline Values
  * Define Timing, Tools & Types of Performance tests
  * Creation of Test Plans
* DEFINE & DESIGN
  * Creation of Test Scenarios
  * Define Test Data
  * Configure Testing Environment
* EXECUTE
  * Execute Test Scenarios
  * Validate Results
  * Record Outcomes
* DELIVER
  * Analyze Results
  * Make Recommendations
  
  
# Services Offered

Our offers load/stress testing services to identify below:
* Identify Performance leaks in the application by doing a performance testing on the applications
* Identify Key areas where performance need to be improved

Our Load Testing model has 3 stages as described below

# Stage 1 – Test Planning Phase

The following activities will be carried out as part of the Test Planning phase:
* Identify performance goals and objectives
* Identify the SLA’s for performance testing
* Define phases for performance testing
* Define Infrastructure
* Identify Load Models
* Identify Volumetrics (Load Mix)
* Identify project support requirements
* Determine the Acceptable test Conditions
* Identify Performance Metrics
* Identify Risks
* Create Performance Test Plan
 

# Stage 2 – Test Preparation Phase
The following activities will be carried out as part of the Test Preparation phase:

* Design Test Data Strategy
* Identify requirements for test data
* Identify Tools for Test data
* Test Environment Setup
* Test environment readiness check [Application deployment and configuration on the dedicated performance test environment ]
* Test Data preparation & pre-requisites validation check
* Test artifacts creation (automated test scripts preparation)
* Dry tests / Validation tests will be carried out for go-ahead on actual tests
 

# Stage 3 – Test Execution and Reporting Phase
The following activities will be carried out as part of the Test Preparation phase:
* Create Performance Test Scenarios
* Execute Environment shakeout
* Execute Baseline/Benchmark tests
* Execute the performance tests
* Analyze test results
* Create Performance test execution report
* Create Performance Test summary repor twith possible recommendations for performance optimization


![1](http://www.abstracta.us/wp-content/uploads/2015/03/why-perf-testing-is-nec-chart-768x463.png)

An Explanation of the Different Types of Performance Testing 
https://dzone.com/articles/performance-testing-vs-load-testing-vs-stress-test

JMeter Ramp-Up: The Ultimate Guide
https://dzone.com/articles/jmeter-ramp-up-the-ultimate-guide


* [What Is Performance Testing? An Explanation for Business People](https://dzone.com/articles/what-is-performance-testing-an-explanation-for-bus)

# Key Performance Indicators (KPIs)
https://www.nd.gov/itd/services/performance-testing


LoadView Hands-on Review Tutorial: Load Testing from the Cloud
http://www.softwaretestinghelp.com/loadview-tutorial/?


https://abstracta.us/tools/introduction-to-taurus-an-alternative-to-jmeter/
https://www.blazemeter.com/blog/taurus-new-star-test-automation-tools-constellation
https://www.theseus.fi/bitstream/handle/10024/118673/Web%20Application%20Performance%20Requirements%20Deriving%20Methodology.pdf?sequence=1
https://www.slideshare.net/ATASlides/continuous-performance-testing-with-taurus-and-jmeter
http://zenq.com/Portals/0/PerformanceTestingWhitePaperrevisedV1.1.pdf


https://abstracta.us/2017/03/24/how-to-make-a-performance-test-plan/
https://abstracta.us/2015/10/12/why-performance-testing-is-necessary/
https://abstracta.us/2017/02/24/best-time-start-performance-testing/
https://abstracta.us/2016/10/17/shutterfly-continuous-performance-testing/
https://abstracta.us/2015/09/14/performance-testing-in-production/
https://abstracta.us/2015/07/30/top-10-factors-that-impact-application-performance/
https://abstracta.us/2015/03/30/free-tools-to-process-logs-for-performance-analysis/
https://abstracta.us/2015/03/30/types-of-performance-tests/
https://abstracta.us/2015/03/30/system-performance-problems/

http://www.abstracta.us/2017/03/16/how-to-make-performance-test-plan/
http://www.abstracta.us/2017/02/24/best-time-start-performance-testing/
http://www.abstracta.us/2017/01/06/gatling-vs-jmeter-findings/
http://www.abstracta.us/2016/10/17/shutterfly-continuous-performance-testing/
http://www.abstracta.us/2016/03/09/why-should-i-become-performance-tester/
http://www.abstracta.us/2016/02/19/jmeter-response-assertions-how/
http://www.abstracta.us/2015/10/12/why-performance-testing-is-necessary/
http://www.abstracta.us/2015/09/14/performance-testing-in-production/
http://www.abstracta.us/2015/09/14/performance-testing-in-production/
http://www.abstracta.us/2016/03/07/checklist-8-ways-to-improve-jmeter-scripts/
http://www.abstracta.us/2015/08/10/software-performance-testing-fallacies-part-1/
http://www.abstracta.us/2015/08/17/software-performance-testing-fallacies-part-2/
http://www.abstracta.us/2015/03/30/free-tools-to-process-logs-for-performance-analysis/
http://www.abstracta.us/2015/05/24/whats-more-important-the-tool-or-the-tester/
http://www.abstracta.us/2015/03/30/types-of-performance-tests/
http://www.abstracta.us/2015/05/18/how-importantnecessary-is-it-for-performance-testers-to-understand-the-architecture-of-systems-and-the-details-on-each-component/

![1](http://fbrnc.net/images/1/2/4/1/6/124165079b019ed1a96340a4e82a9522fe0cfb3e-01cloudwatch.png)
