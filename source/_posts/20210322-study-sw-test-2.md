---
title: Software testing own notes
date: 2021-03-22
tags: [SoftwareTest, Study]
---

# Software testing approach
* Keep in mind
   * [Phase] Test process
      * (In short) Plannig -> Analysis -> Design -> Implementation -> Execution
   * [Type] Test type
      * Functional / Non-functional / White-box / Change-related
   * [Level] Test level
      * Component(Unit) / Integration / System / Acceptance
   * [Evaluation]
      * See https://en.wikipedia.org/wiki/ISO/IEC_9126
      * More likely to use Functionality, Reliability, Usability, Efficiency as QA point of view
         * Of course, Maintainability, Portability are also important as development point of view

# Test strategy in agile
* Think customer first
* (Mindset) Keep "Risk-base" in our mind
* Follow ISO29119 basically, and adapt it into our context
   * https://en.wikipedia.org/wiki/ISO/IEC_29119

# Test plan in agile
* Based on test planning at ISTQB
   * [Scope, Objectives, and risks of testing]
      * Scope: (e.g.) Developed new features and affected existing features
      * Objectives: (e.g.) To achieve product quality which can be released to user at the end of sprint
      * Risks of testing: (e.g.) Feature A is full-scratch so~, feature B has complicated logic so~ 
   * [Defining the overall approach of testing(Test strategy)]
      * See above
   * [Integrating and coordinating the test activities into the software lifecycle activities]
      * See "Process in agile"
   * [Scheduling of test activity, process]
      * Who / What / When / Why
   * [Selecting metrics for test monitoring and control]
      * TBD
   * [Budgeting for the test activities]
      * TBD
   * [Determining the level of detail and structure for test documentation]
      * TBD
* ACC planning
   * I'd prefer this style.
   * https://testing.googleblog.com/2011/09/10-minute-test-plan.html

# Process in agile
* More automation, less manual (From common sense as agile)
   * It depends on context. If automation is difficult, consider to take exploratory testing(e.g. Session-based testing)
      * https://en.wikipedia.org/wiki/Session-based_testing
   * Keep Automation pyramid
      * https://martinfowler.com/bliki/TestPyramid.html
* Practice example
   1. 2wk = 1 sprint
   2. w1.1-5
      * Big developments
      * Analysis/Design/Implementation test
   3. w2.1: testing on new features
   4. w2.1-3: Bug fix, Small developments
   5. w2.4: testing for release
   6. w2.5 release

# Test report
* Should be defined in test plan
* [Important]
   * To gather materials to judge if we can release product to customer or not
   * [Point]
      * Developed features in sprint / Existing features
      * Evaluation of software quality(e.g. Functionality, Reliability)

# Test/QA engineer in agile team
* Always think customer first (Of course, all team members :D)
* Coaching software testing/software quality in team
* Responsible for testing approach in team (e.g. test strategy, test plan)
* Responsible for team productivity (Productivity engineering)
* Maintain tools like scripts, CI

# Test in agile
* [7 Software Testing Principles] Testing is context dependent
   * Need to defind context like target quality, deveopment process in test plan

# Exploratory testing in agile
* Exploratory testing is convenient in agile context since it's not heavy and effective to find bug.
   * [How to use]
	1. To find bug on new features
	2. To check if prodcut can be released
	   * By Session based test: https://en.wikipedia.org/wiki/Session-based_testing
	   * Prepare suitable charter and skilled testers. Need to brush up charter always
* Exploratory testing is just style, not method. Need to define how to use exploratory testing in team

# Scripted test in agile
* (Example) Scripted test covers main user scenario
* Think automation always

# Automation in agile
* Test pyramid -> UT : IT : UI = 7 : 2 : 1
   * https://testing.googleblog.com/2015/04/just-say-no-to-more-end-to-end-tests.html
* Layer
   1. [Low level] Component(Unit) Test
      * Covered logic (File name generator, etc)
      * By JUnit in Android
   2. [Mid level] Integration test
      * Internal sequence between classes
      * By Instrumented test in Android, etc
   3. [High level] UI layer
      * User action/Non functional requirement
      * (Android) By Appium, Uiautomator, Espresso, etc
* Others
   * [Reliability] Monkey(Android)