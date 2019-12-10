# Log Analysis for Mobile Apps

This document discusses:

- Empirical studies in log engineering that we should do
- (Existing) techniques we need to study and develop
- Challenges faced by researchers in mobile log research
- Existing tools/codebases to support researchers
- Overall concerns in mobile logging

Our focus is on logging in the apps (the front-end) unless otherwise indicated.

## Empirical studies in log engineering:

- Why is logging used? Why do mobile devs log? Which logging libraries are used in mobile apps?
  - [https://users.encs.concordia.ca/~shang/pubs/Zeng2019\_Article\_StudyingTheCharacteristicsOfLo.pdf](https://users.encs.concordia.ca/~shang/pubs/Zeng2019_Article_StudyingTheCharacteristicsOfLo.pdf)
- Performance overhead: how much logging is too much?
  - Signal-to-noise levels in the log messages?
  - How to determine the frequency of the logs being delivered back to the developers.
- What do mobile developers use logs for?
  - e.g., Are logs being used for performance monitoring?
  - Why do developers (even) use logs in apps where they cannot read the logs

## Techniques to be studied and developed:

- How much existing techniques should be changed/evolved for mobile apps? Do we need to devise specific tools for mobile?
  - Log analysis research currently focus on Anomaly detection, Security and Privacy, Root cause analysis, Failure prediction, Software testing, Model inference and invariant mining, Reliability and dependability
- How to build different anomaly detection (ML) models for different types of user behavior?
  - In enterprise systems, we have been observing that a single model is not able to capture all the different behaviors of the different companies. We expect the same for mobile apps.
- Can we automatically cluster the different user behaviors?
  - How do we cope with different versions?
    - Maybe Robust Log-Based Anomaly Detection on Unstable Log Data by Zhang et al. might help.
- When do we want to send the logs back to the cloud? And how?
  - Problems: cost, availability/connectivity, energy consumption.
  - Companies like Crashlytics, and Splunk are being by developers.
- How do deal with the inconsistencies and the ever evolving log code base?
  - Robust Log-Based Anomaly Detection on Unstable Log Data. Xu Zhang, Yong Xu, Qingwei Lin, Bo Qiao, Hongyu Zhang, Yingnong Dang, Chunyu Xie, Xinsheng Yang, Qian Cheng, Ze Li, Junjie Chen, Xiaoting He, Randolph Yao, Jian-Guang Lou, Murali Chintalapati, Furao Shen, and Dongmei Zhang
- Can we introduce dynamic logging? I.e., logging only when it&#39;s really needed. Saves energy, bandwidth.
  - Can we send a remote command to start logging that area? i.e., only log when it&#39;s needed? Remember that you can't deploy your app every second, so dynamically activating logs might be a specific problem of mobile apps.
- Security of the logs: before shipping the logs to the cloud, maybe any app can access those logs. How to store them in a secure way?

## Overall concerns:

- Avoid privacy leaks
  - Facebook ad library bug where the facebook token was written to the log, other apps can read
  - GDPR in EU.
    - Who is liable to check if the logging/log files in the apps are compliant?
    - If you use your 'own logging library to collect data', do you have to ask permission for the user? (Note that for logs you get in the app store, directly from Google, you don't need, as Google already asked for it)
  - As a user, do you know what&#39;s being logged about you?
- Size of the applications. Mobile apps are often smaller than enterprise traditional projects. Mobile apps focus on single tasks
- Is scalability as big of an issue as in other domains, e.g., enterprise applications?
- Who is responsible to make sure that the log frameworks are good-faith actors who do not have backdoors in the logging.
- How much of the localization of log lines impact the tools and techniques?

## Research challenges:

- We need log datasets from mobile applications
  - LogPai benchmark: [https://github.com/logpai](https://github.com/logpai), but it does not consider mobile apps.
- Representative datasets of mobile apps source code
  - FDroid might be not that representative...

## Existing tools:

Note: [ISNIT0](https://github.com/ISNIT0) is Joseph Reeve&#39;s github account. Joe works with [Julian Harty](https://github.com/julianharty) on creating code to help research logging, mobile analytics.

- [https://github.com/ISNIT0/AndroidCrashDummy](https://github.com/ISNIT0/AndroidCrashDummy) a small exploratory/demo app to test/exercise other aspects of logging and analytics
- [https://github.com/ISNIT0/AndroidLogAssert](https://github.com/ISNIT0/AndroidLogAssert) a Log Assertion Library for use with Android Espresso tests
- [https://github.com/ISNIT0/logcat-filter](https://github.com/ISNIT0/logcat-filter) Logcat-filter and analysis tool
- [https://github.com/ISNIT0/log-searcher](https://github.com/ISNIT0/log-searcher) A tool for searching Android codebases and analysing usage of &quot;Log.\*&quot;
- [https://github.com/ISNIT0/log-complexity-comparison](https://github.com/ISNIT0/log-complexity-comparison) This tool helps find complex code that does not have much logging to back it up. It was originally built to help with research done by Julian Harty and Joseph Reeve on logging placement. The output is a JSON file and an HTML report, describing which files need more logging attention.

## Logging by the Operating System

Google Android includes logging at the device level. Users have the option to opt-in/out to automatically provide usage and diagnostics data to Google [Play]. This logging includes usage, crashes, ANRs and performance issues.

## Authors

- Meiyappan Nagappan
- [Julian Harty](https://github.com/julianharty)
- [Maurício Aniche](https://www.mauricioaniche.com)
- Luca Pascarella
- Weiyi Shang
