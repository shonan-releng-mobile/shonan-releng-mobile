# Artefacts for Release Engineering of Mobile Apps
https://docs.google.com/document/d/1d4Xmv-Mql25whIYZRCckuz6S0kw4CKTk-2CFZGgZVKY/edit?usp=sharing




![Overview](artefacts.png)



## Different Sources:

- User facing:
	- social media (reddit, blogs, twitter, FB, forums)
- Developer facing
	- app stores
    	- Apple, Google, Steam (commercial)
    	- F-Droid (probably not representative), Linux Package Managers ... (open source)
	- app releases (app lineage)
	- commit history
	- StackOverflow Discussion
	- Android Framework Evolution
- In between:
	- Logs
	- Crash Reports
	
	
## Pipeline

| RelEng Phase                 | Artifacts |
| ------------------------     | -------------------- |
| **Requirements Engineering** | social media        |
| Integration                  | Open Source App Stores (e.g., F-Droid)  |
| Build + Test                 | Git, CI Providers |
| Deployment                   | app lineage |
| **Monitoring + Reaction**    | logs, social media   |

The bold phases are the ones that can benefit most from the use of social media.
We can use posts as indicators of the release process or to mine new requirements.
