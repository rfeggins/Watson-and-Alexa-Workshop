# Test Automation Strategy for Agile Projects

## Executive Summary 
In today’s competitive climate with app being measured not only by their capabilities but also their social score, it’s often better to release one “rock solid” feature rather than several poor quality or poor performing features.
At a minimum, your automation strategy must ensure that any newly developed features don’t introduce any regression defects, so automating regression testing is the first order of business.

As teams move toward continuous integration (CI) / continuous delivery (CD), test automation becomes a core activity used to provide teams with the rapid feedback loop required for the development teams to better understand the health of the application under development.

In this post we will provide an overview of test automation concepts, practices and tools.

## Test Automation Basics
Here are several items that should be considered in order to get this quick feedback as part of the development of new features. The automated test cases should be
1.	Executed continuously as part of the both the CI and CD deployment cycles to reduce the possibilities that test resources waste time with test unstable builds 
2.	Fast providing rapid test results that can be used to make quick course corrections to the upcoming code changes
3.	Planned as part of a coherent testing approach where quality is “baked in” right from the start

This approach often requires “inverting the test automation pyramid” by pushing down GUI tests that take a long time to execute, to lower levels e.g. API layer that can run straight after unit tests as part of the build to provide the initial level of confidence.
hich we can obtain feedback quickly is formulated.

As already mentioned, quick feedback on the health of the application is of huge importance to support continuous delivery, therefore, a process and a mechanism by w
Automating testing is one of the key components needed to successfully implement an overarching Agile Test Strategy.  In this document we will share several of the key points that should be considered to get the most out of your existing test assets.  This strategy assumes that the project is using a continuous delivery model where several agile teams (e.g., Agile Release Train) must work together to deliver a complex software solution.  

>
> KEY POINT	Quality should be favored over quantity. 
>

The first element of any effective test automation effort is creating and automating the Unit testing performed by the developers.  Unit testing is the foundations of any test automation effort. 
The second element of improvement is running the regression tests more frequently and aligned with the process of Continuous Integration, see later. 

Automation Testing should not be seen as an isolated task, but rather as a coherent activity embedded in the process. Increasing the number of unit tests, integration tests, and API tests execute as part of a CI build suite often ensures that the code changes are working at least at a basic level.
Defining Regression Test Scenarios.

Automated regression tests are the core of the Test Automation Strategy. Here are thrie
- Smoke testing
- Functional testing
- End to End Testing

### Smoke Testing, 
Smoke Testing is a subset of the full regression test assets used to sanity check the application before deploying it for additional testing such as load or user acceptance testing. Keep the number of test cases  run to just a few to make sure application is still functional.
Rule of thumb, if the common user flow cannot be loaded and smoke tests completed in less than 5 minutes than you need to fail the tests as is something major is probably not working.
The smoke test pack runs on every CI build / deploy and should be a mixture of API and/or GUI tests.

### Functional Testing 
Functional Testing is meant to check the application functionality in more detail than the smoke testing. 
Typically each team has several different test suites (e.g. regression packs) used for different purposes. If there are multiple teams working on different parts of the application, then each team will have their own regression packs focusing on the area that they are working on.
These packs should be able to run in any environment as and when required, provided the behavior of the features remain consistent throughout the environments. They are executed multiple times a day and should last no longer than 15 to 30 minutes.

As these functional tests are more detailed, then they will take longer to run therefore, it is important to have the majority of functional tests at API layer where tests can be executed faster so we could be within the 15 to 30 minutes time limit.
End-to-End Regression Pack, which tests the whole application as a whole. The aim of these tests is to ensure that various parts of the application which connect to various databases and third-party applications work properly.

### End-to-End testing
The End-to-End tests are not meant to test all of the functionalities as those are already tested in the functional regression packs, however, these tests are “light-weight” which just check the transitions from one state to another and a handful of the most important scenarios or user journeys.
These tests are mainly executed through the GUI, as they are checking how users would use the system. The time taken to execute these can vary from one application to another but they are usually run once a day or night.
