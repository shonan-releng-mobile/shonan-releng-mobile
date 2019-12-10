# What Makes Mobile Special for Releng?

## Differences between App Store and Package Manager

We analyzed the main differences between those two providers. In case of App store the focus is on releasing application for general users, while the package manager focuses on releasing libraries for a limited audience (e.g., CS users).

During our discussion we realized that app stores are conceptually an extension of package managers. The main features provided together with the app stores are:

- More direct interaction with the users
- There are several ranking criteria for users (e.g., downloads, scores)
- Mobile Apps are expected to provide revenues
- Libraries packaged together with the mobile app cannot be downloaded
- The approval process is more strict
- Mobile apps require permission from the user
- One point of sale
- Large population and more diverse users

This motivates the need for addressing the following challenges in release engineering for mobile apps.

## Challenges for Mobile-app release engineering

- Design testing strategies for non-functional requirements. Especially in case of small companies, testing for accessibility, usability, and energy consumption might be challenging.
- Setting-up the testing infrastructure is more difficult to the fragmentation
- A/B Testing is more complex
- To address complaints in the reviews there is the need for releasing fast. However, the approval process is quite slow and prevent rapid releases.
- Because of the need for super-fast releases, typicall development activites as code review need to be improved.
- Traceability bugs <-> bad reviews.

# Authors
Mei, Daniel, Carmine, Luca, Kla, Masa, Fabio, Lili, Cuiyun

# More

https://docs.google.com/document/d/1ZUYPZstcFJXRW2h7ahGXrm3hG1ci2sOLZ7m6tUq3bGw/edit?usp=sharing
