# cloud-foundry-deploy

Deploys the current path to a Cloud Foundry instance. Current version of cf:
6.10.0.

# What's new

- Fix cf on version 6.10.0
- Blue-Green Deploys.
- Support for hosted Cloud Foundry instances.

# Options

* `appname` (required) The application name.
* `username` (required) Cloud Foundry Username.
* `password` (required) Cloud Foundry Password.
* `organization` (required) Cloud Foundry Organization.
* `space` (required) Cloud Foundry Space.
* `alt_appname` (optional) Alternative application name for blue-green deploys.
* `domain` (optional) App domain.
* `route` (optional, required for blue-green deploys) App route.
* `api` (optional, default: `https://api.run.pivotal.io`) Cloud Foundry API endpoint.
* `skip_ssl` (optional) Skip SSL validation on API login.

# Example

Deploy to Cloud Foundry:

```yaml

deploy:
    steps:
        - wercker/cloud-foundry-deploy:
            api: $CF_API # Set as environment variables
            username: $CF_USER
            password: $CF_PASS
            organization: $CF_ORG
            space: $CF_SPACE
            appname: myapp-green
            alt_appname: myapp-blue
            route: default_app.cfapps.io
```

# License

The MIT License (MIT)

# Changelog

## 1.0.0

- Fix cf on version 6.10.0
- Blue-Green Deploys.
- Support for hosted Cloud Foundry instances.
