# Atomist 'spring-boot-rest-service'

[![Build Status](https://travis-ci.org/atomist-rugs/spring-boot-rest-service.svg?branch=master)](https://travis-ci.org/atomist-rugs/spring-boot-rest-service)
[![Slack Status](https://join.atomist.com/badge.svg)](https://join.atomist.com)

This Rug archive contains a generator for a Spring Boot Rest Service project.

## Rugs

### NewSpringBootRestService

The NewSpringBootRestService Generator creates a new [Spring
Boot][boot] [REST][rest] service project.

[boot]: https://projects.spring.io/spring-boot/
[rest]: https://en.wikipedia.org/wiki/Representational_state_transfer

[<img src="http://images.atomist.com/button/create-project.png" width="267" alt="Create a project with Atomist"/>](https://api.atomist.com/v1/projects/generators/16271c54-e671-4be6-a30c-084aba8083ed)

#### Prerequisites

There are no prerequisites to running this generator.

#### Parameters

To run this generator you must supply the following parameters.

Name | Required | Default | Description
-----|----------|---------|------------
`project_name` | Yes | |  A valid GitHub repository name.  It must be 21 characters or less to avoid truncating name when the its Slack channel is created.
`artifact_id` | No | myartifact | Maven artifact ID, e.g., "fiddle-riddle".
`group_id` | No | mygroup |  Maven group ID, e.g., "com.pany.project".
`version` | No | 0.1.0-SNAPSHOT | [Semantic version][semver] of the project.
`description` | No | My new project | A brief description of the project.
`root_package` | No | com.myorg | The root package for the generated service class.
`service_class_name` | No | MyService | Name for the generated service class.

[semver]: http://semver.org

#### Running

Run it as follows:

```
$ cd parent/directory
$ rug generate atomist-rugs:spring-boot-rest-service:NewSpringBootRestService \
    pet-shop-service \
    artifact_id=pet-shop \
    group_id=uk.co.lndn \
    version=0.1.0-SNAPSHOT \
    description="Spring Boot REST service for selling stuff" \
    root_package=uk.co.lndn.electronic \
    service_class_name=PetShop
```

Note the first parameter, the `project_name`, is different in that you
do not need to supply the name of the parameter, just the value.  This
is because the `project_name` parameter is required for all
generators.  This will create a directory named `pet-shop-service` and
populate it with a working Spring Boot REST service.  If you are happy
with the change, commit the changes.

```
$ cd pet-shop-service
$ git init
$ git add .
$ git commit -m 'Initial version generated by Atomist'
```

See the README in the generated project for further instructions.

## Support

General support questions should be discussed in the `#support`
channel on our community Slack team
at [atomist-community.slack.com][slack].

If you find a problem, please create an [issue][].

[issue]: https://github.com/atomist-rugs/spring-boot-rest-service/issues

## Development

You can build, test, and install the project locally with
the [Rug CLI][cli].

[cli]: https://github.com/atomist/rug-cli

```
$ rug test
$ rug install
```

To create a new release of the project, simply push a tag of the form
`M.N.P` where `M`, `N`, and `P` are integers that form the next
appropriate [semantic version][semver] for release.  For example:

[semver]: http://semver.org

```
$ git tag -a 1.2.3
```

The Travis CI build (see badge at the top of this page) will
automatically create a GitHub release using the tag name for the
release and the comment provided on the annotated tag as the contents
of the release notes.  It will also automatically upload the needed
artifacts.

---
Created by [Atomist][atomist].
Need Help?  [Join our Slack team][slack].

[atomist]: https://www.atomist.com/
[slack]: https://join.atomist.com/
