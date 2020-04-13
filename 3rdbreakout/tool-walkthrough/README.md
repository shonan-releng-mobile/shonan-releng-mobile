# Walkthrough of Releng Tools used by several opensource Android apps
The walkthrough was a live demonstration by Julian Harty focusing primarily on Google Play Console including two integrated facilities: 1) Release Engineering and 2) Android Vitals analyics and reporting. We also performed very brief walkthroughs of the continuous build processes for several Android apps.

# Google Play Console
Google Play Console is the interface Google provides primarily for developers of Android apps in the Google Play Store. It is intended to provide developers with tools, reports, and insights about how their apps are performing in terms of pupularity, usage, revenues, stability, ratings and reviews. Developers (with appropriate permission) can also manage releases from both a testing and in terms of managing production releases.

Each app belongs to an owner, who will have registered as a developer and paid a one-time fee. Owners can share aspects of their account with other people who have a Google account and who have accepted Google's terms and conditions, etc. The sharing can be granular and limited to a single app owned by a particular owner, the owner can also set the permissions that these other people will have for one or more apps they own. Individuals can have access to multiple accounts and distinct permissions for each app and/or account.

## Release Management

## Android Vitals

# The apps
Julian Harty has been involved in each of the following projects and therefore able to introduce the tools used by each project and aspects of the development, testing, and release processes. In each case there are lead developers for the particular who may be willing to provide further details and insights related to Release Engineering.

- Android Apps from the catrob.at team at TU Graz (source code https://github.com/catrobat/, project homepage https://www.catrobat.org/, JIRA https://jira.catrob.at/, CI https://jenkins.catrob.at/)
- Android Apps from the Kiwix team (source code https://github.com/kiwix/kiwix-android/, project homepage https://www.kiwix.org/). (note: currently migrating from travis-ci [Kiwix on Travis-CI](https://travis-ci.com/github/kiwix/kiwix-android) to GitHub Actions, [GitHub Actions for Kiwix](https://github.com/kiwix/kiwix-android/actions)).
- Android Apps from the eduVPN project (source code https://github.com/eduvpn/android, project homepage https://eduvpn.nl/). A proof-of-concept CI is on Travis-CI https://travis-ci.com/github/commercetest/android

# CI and CB
## Characteristics of the Build Process for these apps
Each project team has a distinct build process. Of these, the build process and tooling for the Catrobat apps is the most sophisticated and mature. 

### Kiwix
The Kiwix Android codebase incorporates a library written in C++ that is shared across many Kiwix projects (including web servers and the iOS app). There are distinct codebases, on GitHub, for the library and for shared build processes and tools. Development builds use pre-built binaries for the native code. 

### Catrobat apps
The Catrobat apps are built using a farm of Jenkins servers. 

### eduVPN
The app is independently built by a developer who does not work directly on the development of the app's codebase. 

## Characteristics of testing for these apps
### Kiwix

Until the end of 2019 the project used a combination of Travis-CI and TestDroid to run the automated tests on several hosted physical devices.

### Catrobat apps
Automated tests are run by Jenkins. 

### eduVPN
Testing is ad-hoc and best described via one of the project's 'issues': [eduVPN issue 221](https://github.com/eduvpn/android/issues/221)


## Characteristics of the Release Engineering for these apps

### Elapsed times

- Kiwix app
- Custom Kiwix apps:
    - WikiMed
    - ...
- eduVPN
    - eduVPN
    - Home edition (not currently in a CB)
- Catrobat
    - PocketCode
    - PocketPaint

### Glossary 

- CB: Continuous Build
- CI: Continuous Integration
