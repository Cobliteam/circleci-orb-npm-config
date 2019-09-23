# npm-config for CircleCI

[CircleCI Orb](https://circleci.com/docs/2.0/orb-intro/) commands to change NPM configurations

## Commands

### set-repository

```yaml
version: 2.1
orbs:
  npm-config: cobli/npm-config@x.x.x
jobs:
  test:
    docker:
      - image: circleci/node:9.11.2
    steps:
      - checkout
      - npm-config/set-registry:
          registry-prurl: //your.repo.hostname/registry/
          scope: "@your-scope"
          auth-token: "your-repo-token"
      - run:
          name: Download depencies
          command: yarn
      - run:
          name: Test
          command: yarn test

```