# Free Software Licensing 

```mermaid
graph TD

IdentifyProject[Identify the independent works] --> Identify3rdParty
Identify3rdParty[Identify Third party material (“Libraries”) — by reference & local] --> UpstreamLocation
UpstreamLocation[Identify the upstream location of the 3rd party materials] --> Problems
Problems[Identify any licensing problems] --> NoProblems
Problems --> unlicensed[unlicensed materials]
NoProblems[Choose license of the program] --> LicenseChoice
LicenseChoice{Choose your license} --> contractRequirements
contractRequirements[Identify contract requirements] --> CreatLicense
CreatLicense[Create LICENSE file] --> UpdateReadme[update README]
```
