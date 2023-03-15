# Free Software Licensing

```mermaid
IdentifyProject[Identify the independent works] --> Identify3rdParty
Identify3rdParty[Identify Third party material by reference & local] --> UpstreamLocation
UpstreamLocation[Identify the upstream location of the 3rd party materials] --> Problems
Problems[Identify any licensing problems] --> NoProblems
NoProblems[Choose license of the program] --> LicenseChoice
Problems --> unlicensed[unlicensed materials]
LicenseChoice{Choose your license} --> contractRequirements
contractRequirements[Identify contract requirements] --> CreatLicense
CreatLicense[Create LICENSE file] --> UpdateReadme
UpdateReadme[update README]
```
