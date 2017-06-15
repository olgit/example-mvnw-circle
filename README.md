# Black Duck CoPilot Maven-Wrapper/Circle CI Example


[![CircleCI](https://img.shields.io/circleci/project/github/BlackDuckCoPilot/example-mvnw-circle/master.svg)](https://circleci.com/gh/BlackDuckCoPilot/example-mvnw-circle) [![Black Duck Security Risk](https://copilot.blackducksoftware.com/github/groups/BlackDuckCoPilot/locations/example-mvnw-circle/public/results/branches/master/badge-risk.svg)](https://copilot.blackducksoftware.com/github/groups/BlackDuckCoPilot/locations/example-mvnw-circle/public/results/branches/master)

Shows a working setup for using the Black Duck CoPilot integration to analyze the risk of project dependencies

## Circle CI Setup

The `circle.yml` file has been modified to upload the generated data to Black Duck CoPilot:

```yaml
test:
  post:
    - ./mvnw com.blackducksoftware.integration:hub-maven-plugin:2.0.0:build-bom -Dhub.output.directory=. -Dhub.deploy.bdio=false
    - bash <(curl -s https://copilot.blackducksoftware.com/bash/circle) ./*_bdio.jsonld
```

