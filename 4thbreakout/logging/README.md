# Logging in the mobile world

We define three goals:

1. Understand what "external logs" look like.
1. Explore the differences between internal log vs external log
1. Understand the performance impact of external logs

## G1: Understand what "external logs" look like.

* Why do developers log?
* What do developers log? Are they concise?
* How do they log? In which format, e.g., JSON, unstructured text?
* What are their concerns when logging?
* Understand how external logs evolve over time

Methodology:

* Use open-source projects and analyse their repositories and source code, looking for external logs. <End of January, we will have a skype meeting to disucss progress on this item.>
	* We have access to their source code, so we can fully analyze their logging code.

* Observe the logs that are produced by real-world applications, like Facebook, Instagram, etc etc, which we have no access to the source code.
	* Observational study: We can create an app that (with the user permission) collects the logs of the applications they are using. We then analyse this data.
	* Advantages: "Logging in the wild", real-world data
	* Disadvantages: we have less control about how people are using those apps.
	* Can we use mechanical turk for that?

* Timelines for adoption of logging libraries
	* History of providers e.g. Flurry, Firebase, Fabric, ...
	* "Market share" of logging libraries, which apps contain which libraries? See https://appbrain.com/ 
	
* Reflected logging (using server logs to reflect behaviours of the app)
	* For example, back-end server logs may provide information and effectively log usage of the app(s) that use these servers. Some usage may be user-initiated, others from code in the app e.g. to predictively download content.

## G2: Explore the differences between internal log vs external log

Internal logging: the log "stays only in the device". _Note: Internal logging can be in-memory or in a place where other apps can see_
External logging: the log goes to some external cloud service.

* Study when developers started to use these external logging providers and why
	* appbrain.com (former Googlers) might give us some insights on this
	* Methodology: analysis of the code repository, looking for commits that introduced the logging


## G3: Understand the performance impact of external logs

* From the perspective of the app, i.e., does the app get much slower because of that?
* Understand the performance of the logging framework themselves, i.e., how much it costs to log more information or less information. The comparison was done with log4j, where printing the class name or the line number just costs more than just printing a text message.

Methodology:

* Understand how the state-of-the-practice tools work
	* When do they send the logs?
	* Do they zip the logs?
	* Do they send all the data or just the 'last events'?
	* Discuss the limitations of these decisions

* Measure the performance of the logs in real-world apps
	* Remove the log line and see the impact on performance, energy consumption, network usage.

* Micro-benchmark the logging frameworks for mobile
	* Understand the costs of the different logging operations, e.g., adding more information, line number, etc etc, what's the impact on performance, energy consumption, network usage?

## A bigger holistic view

How does this compare to enterprise and open-source logging strategies?

## Ethical implications

* If we are collecting logs of other apps, what are the privacy (as well as GDPR) concerns we have to take into account?

## Related Work

* Yi Zeng, Jinfu Chen, Weiyi Shang and Tse-Hsun Chen. Studying the Characteristics of Logging Practices in Mobile Apps: A Case Study on F-Droid. Empirical Software Engineering. 
https://users.encs.concordia.ca/~shang/pubs/Zeng2019_Article_StudyingTheCharacteristicsOfLo.pdf
* Shaiful Chowdhury, Silvia Di Nardo, Abram Hindle, Zhen Ming (Jack) Jiang "An exploratory study on assessing the energy impact of logging on Android applications" https://link.springer.com/content/pdf/10.1007%2Fs10664-017-9545-x.pdf
* Device Analyzer: usage of smartphones https://deviceanalyzer.cl.cam.ac.uk/ links to several papers.

## Authors

* Maurício Aniche
* Julian Harty
* Luca Pascarella
* Lili Wei
* Weiyi Shang

