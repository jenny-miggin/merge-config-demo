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

This means that both configs will be merged at runtime 