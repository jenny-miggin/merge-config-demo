# Merge Config Demo

## Intro

In the `selectively-merge-config` branch, there are 2 paths.

### How does it work?

In `service1/.circleci/config.yml` there is a standard workflow

But, there are also dependencies listed in `service1/.circleci-config-dependencies` which list the configs that will be merged at runtime if there are changes anywhere in `service1`. In this example, here are the dependencies:

```yml

service1/.circleci/config.yml
library1/.circleci/config.yml
```

This means that both configs will be merged at runtime if there are any changes within `service1`

### What would be the use case for this?

If, for example, there are changes to a service, you may want to ensure that the library that the service depends on is fully up-to-date, tested and deployed. This also means that changes to `library1` do *not* trigger a pipeline
