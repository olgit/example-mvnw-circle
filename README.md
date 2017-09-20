# Black Duck CoPilot Maven-Wrapper/Circle CI Example


[![CircleCI](https://img.shields.io/circleci/project/github/BlackDuckCoPilot/example-mvnw-circle/master.svg)](https://circleci.com/gh/BlackDuckCoPilot/example-mvnw-circle) [![Black Duck Security Risk](https://copilot.blackducksoftware.com/github/repos/BlackDuckCoPilot/example-mvnw-circle/branches/master/badge-risk.svg)](https://copilot.blackducksoftware.com/github/repos/BlackDuckCoPilot/example-mvnw-circle/branches/master)

Shows a working setup for using Black Duck CoPilot to analyze the risk of project dependencies

## Circle CI Setup

The `circle.yml` file has been modified to upload the generated data to Black Duck CoPilot:

```yaml
test:
  post:
    - bash <(curl -s https://copilot.blackducksoftware.com/ci/circle/scripts/upload)
```
