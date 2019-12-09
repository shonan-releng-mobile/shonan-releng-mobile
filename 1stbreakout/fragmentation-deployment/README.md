# Overcoming Fragmentation for Deployment

## Definitions

Pull-deployment model

Frontend & Backend versioning

App Reviews vs. Release logs

Fragmentation

A web app:
Build -> Deploy -> Release

A mobile app:

```
  Controlled by the dev
+---------------------------+
| Build -> Deploy          -|-> App Store (The pull request happens here) -> Release (The user may not accept the new release)
|      \-> Backend release  |
|                           |
+---------------------------+
```

## Challenges

Misaligment on Frontend & Backend

Tracebility of app reviews to an app version (and therefore to a changelog)

Tracebility between user and developer artifacts

Can't force users to update

Support legacy software

## Research directions

Feature toggle updates to emulate canary updates (How to get them right and proper)

Factors that drive changes and updates to the users
  (What is a good release note that make people want to update faster?)
  
Usage of network logs for aproximating the backend behaviour
Compare the behaviour of the webapp to the frontend against the same backend
