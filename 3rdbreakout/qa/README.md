# Quality Assurance for Mobile Apps

## How does industry define QA?

* Check: basically static analysis
* Testing: more like exercising the app

* Artifacts that need to be tested:
	* Software code
	* Resource files
	* Unit tests
	* Test in platform (by means of an emulator)
	* Many devices

## What are quality attributes for mobile?

* Number of bugs, as it was always done?
* Can we use *user rating* or *satisfaction* as quality attribute?
	* Is that what we should care more about?
	* Why similar apps have higher ratings than others?
	* What do an app need to be successful? What does it mean 'to be successful'?
* Performance
* Energy consumption

## Overall QA pipeline:

1. Static analysis
1. Prediction
1. Code reviews
1. User reviews
1. Automated testing
1. (to be continued)

## Static analysis for mobile apps:

* Can we use existing tools, like Findbugs for mobile? Yes.
* Specific for Android: *AndroBugs*. Vulnerability scanner, linters.
* Still not enough, lots of false positives. Use of basic/simple rules.
	* This is a general problem in static analysis (not only for mobile)
	* Android's linter has accessibility checks.
* Do we have a tool that statically checks for energy consumption, accessibility, or other non-functional requirements?
* Challenges: obfuscation, multi-language development (e.g., in Android, codebases have Java and C) <-- maybe a challenge for black box testing?

Open questions/challenges:

* What are the characteristics of non-functional bugs?
	* We need patterns/anti-patterns for detecting energy consumption, accessibility, usability, etc.
	* See paper by Luis Cruz et al. (EMSE special issue on mobile apps)
* How well can we develop static analysis to detect non-functional problems?
* How can we design static analysis for resources?
	* See paper by Suelen Goularte et al. (EMSE special issue on mobile apps)
* Can we design tools/techniques that are platform-agnostic, or do they need to be platform-specific?


## Prediction

* Do we need defect prediction techniques? They are small files, so maybe you need less prioritization.
	* Maybe we need more defect localization, rather than prediction.

## Code reviews

* We can't see differences when it comes to code review in traditional apps.
* RQ: What is different when reviewing mobile apps? Do they actually do it?
	* Maybe related to the non-functional differences we discuss before.
* In a lot of small apps, there's just one developer. Is there a need for code review?
	* Self-review might still be useful. Ex: if you program in VS Code, and review it on Gerrit, the difference in the IDE might help you in seeing things you don't.

## Leveraging user reviews

* How to extract bug reports from user reviews?
	* Lots of papers on this topic already
* User reviews are noisy
	* We need NLP approaches to remove noise

## Testing

* Challenges:
	* Fragmentation
	* (Environment) dependencies
	* Interactions with other devices

* Tools exist for UI testing, such as Facebook's one
	* Monkey testing is still the best (by Alex Orso)

* From a pragmatic point of view:
	* Apps are made of a lot of UI code, which is hard to unit test.
	* When to do unit testing or when to do system tests for Android?
	* Mocking is a way, but in a UI-heavy application, do we want to mock the UI?
	* RQ: What kind of tests do developers really **do** in practice? What kind of tests they really **need** in practice?
	
* Can we do (automatic) crash reproduction? 
	* Julian: We would be ok if the reproduced crash is not an end-to-end. If it's a "unit test" (one, two, three classes), that'd be already useful for the developer to start working on the issue. 

## Big questions

* Should we help the 'big app developers' or the 'small app developer' (who are a huge part of the market)?
* Can we learn the best QA practices from the data/developers we have available?
* Given limited resources, what type of tests should we do?
