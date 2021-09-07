---
description: Modify your first component
---

# Microservice

In this tutorial, you will be changing the `mock-data` service, deploying the change and reviewing the change behind its feature flag in production.

Before you start, make sure you have [set up](../back-end.md) your local development environment.

#### 1. Clone service

```text
git clone https://github.com/avidaml/mock-data.git
```

#### 2. Add a customer entity

Dynamically \(in code\) add a new entity to the list of mock entities. While mock entities are initially loaded from a JSON file, you will need to add the entity after loading from JSON so you can apply a feature flag to show or hide the change.

[Show me how]()

#### 3. Add a feature flag

Wrap your change in a [feature flag](../../contributors/feature-flags.md) so that the newly added customer will only be visible to you.

#### 4. Step through changes

Use the VS Code debugger to step through code changes.

#### 5. Run unit tests

```text
make test
```

The tests should fail because the customer count has changed. Fix the broken test and rerun.

#### 6. Commit changes

Commit your changes to trigger the build and deployment pipeline. If your tests pass, the change will be deployed to production.

#### 7. Confirm deployment

Check the service's [pipeline](https://app.circleci.com/pipelines/github/avidaml) in CircleCI to determine whether your change was successfully deployed.

#### 8. Test change in production

Delete existing mock data \(Profile &gt; Settings &gt; Remove sample data\) and re-add mock data to introduce your changes.

Test with the feature flag on and off.

#### 9. Review Instana for issues

Check Instana event logs

### Revert changes

Revert your changes and redeploy. Remove the feature flag.



