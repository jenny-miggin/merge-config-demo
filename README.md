# Merge Config Demo

## Intro

In this repo, there are 2 paths.

Regardless of any changes in sub-directories, the main workflow in `.circleci/config.yml`, and the shared jobs within this, will always run

### How does it work?

Firstly, there are dependencies listed in `service1/.circleci-config-dependencies` which list the configs that will be merged at runtime if there are changes anywhere in `service1` directory. In this example, here are the dependencies:

```yml

service1/.circleci/config.yml
library1/.circleci/config.yml
```

This means that both `config.yml` files listed will be merged at runtime if there are any changes within `service1`

If there are any changes to `service2`, then just that config (`service2/.circleci/config.yml`) will be used as there are no dependencies

### What would be the use case for this?

If, for example, there are changes to a service, you may want to ensure that the library that the service depends on is fully up-to-date, tested and deployed. This also means that changes to `library1` do *not* trigger a pipeline
