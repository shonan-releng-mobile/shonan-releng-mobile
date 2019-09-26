# shonan-releng-mobile
## Meeting overview 
Release engineering is the process that ships code changes from a developer’s workspace to the end user [1]. It encompasses tools and technologies to accomplish continuous integration, deployment, delivery, and experimentation, such as build specifications, infrastructure-as-code, containerization, and many more.

In recent years, there has been a renewed interest in this area, driven by the need to deliver new content to users in a continuous fashion. For example, popular web browsers like Mozilla Firefox and Google Chrome have shifted from slow, semi-annual releases to rapid, six-week release cycles. In the domain of web applications, where control over the main delivery process is retained, industry has produced innovative techniques to achieve continuous delivery of new content. These techniques allow for new content to be tentatively released (e.g., canary deployment), seamlessly released (or rolled back) without customer-facing downtime (e.g., blue- green deployment), and analytically evaluated with data from the field (e.g., A/B testing).

At the same time, mobile applications have become a typical means of delivering content to users. For example, recent market studies show that about four billion mobile devices are connected in 2017 [2] and predict that the global mobile app economy is expected to be worth $157 billion by 2022 [3].

Rather than delivering content directly through the web browser, mobile app users install applications on their mobile devices (e.g., smartphones, tablets). Release engineers need to deliver new releases from a software organization to app stores that curate mobile apps and make them available to users. The existence of third-party app stores in the release path from software organization to user poses several challenges:

- Users must opt-in to an update of the client-side app in order for new content to be delivered. Releasing too quickly creates an overhead for users, since downloading and installing updates may slow down access to apps. Moreover, with the explosive growth of mobile app sizes, users may need to pay expensive data fees for large downloads on cellular networks.
- App stores act as a bottleneck between software organizations and users, which may impose delays in the release process. For example, to prevent malware and exploit- vulnerable apps from impacting users, all of the apps that appear in the Apple app store need to be certified by an Apple technician. This certification process is slow, cumbersome, and expensive.
The purpose of this Shonan meeting is to bring together leading researchers and practitioners from the release engineering and mobile apps fields. The aim is not only to foster an exchange of ideas, but also to outline a clear set of concrete grand challenges and propose a roadmap for how those challenges can be met by future work. To accomplish our goal, we will follow the schedule:

A tangible outcome of the Shonan meeting will be a manuscript that describes the grand challenges and our roadmap for future research. For example, a foreseeable grand challenge is how software organizations can achieve crowd-based deployment strategies that have become so popular for web applications (e.g., canary and blue-green deployment) in a mobile setting. The produced manuscript will be submitted as a vision paper to a conference or journal.

### References
[1] B. Adams and S. McIntosh. “Modern Release Engineering in a Nutshell: Why Researchers should Care.” In Proceedings of the 2016 IEEE International Conference on Software Analysis, Evolution, and Reengineering, Future of Software Engineering track, pp. 78–90.

[2] A. Pappas. “Developer economics: App market forecasts 2013-2016.” Online:  https://is.gd/PMqft8, Last accessed Jun 2018.

[3] S. Cheney and E. Thompson. “The 2017-2022 App Economy Forecast: 6 Billion Devices, $157 Billion in Spend & More.” Online: https://is.gd/61uIoy, Last accessed Jun 2018.
