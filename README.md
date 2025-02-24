# Important
This fork has @klaveness/cypress-configuration removed from the package.json dependencies, you need to install it from [here](https://github.com/Klaveness-Digital/cypress-configuration) manually since there was an issue that prevented this repo from being installed using npm.
# cypress-cucumber-preprocessor

This preprocessor aims to provide a developer experience and behavior similar to that of [Cucumber](https://cucumber.io/), to Cypress.

## Installation

See [badeball/cypress-cucumber-preprocessor](https://github.com/badeball/cypress-cucumber-preprocessor) for a public, community-maintained edition and installation instructions.

## Introduction

The preprocessor (with its dependencies) parses Gherkin documents and allows you to write tests as shown below.

```cucumber
# cypress/e2e/duckduckgo.feature
Feature: duckduckgo.com
  Scenario: visting the frontpage
    When I visit duckduckgo.com
    Then I should see a search bar
```

```ts
// cypress/e2e/duckduckgo.ts
import { When, Then } from "@klaveness/cypress-cucumber-preprocessor";

When("I visit duckduckgo.com", () => {
  cy.visit("https://www.duckduckgo.com");
});

Then("I should see a search bar", () => {
  cy.get("input").should(
    "have.attr",
    "placeholder",
    "Search the web without being tracked"
  );
});
```

## User guide

For further documentation see [docs](docs/readme.md) and [docs/quick-start.md](docs/quick-start.md).

## Contributing

See [badeball/cypress-cucumber-preprocessor](https://github.com/badeball/cypress-cucumber-preprocessor) for a public, community-maintained edition and contribution instructions.

## Building

Building can be done once using:

```
$ npm run build
```

Or upon file changes with:

```
$ npm run watch
```

There are multiple types of tests, all ran using npm scripts:

```
$ npm run test:fmt
$ npm run test:types
$ npm run test:unit
$ npm run test:integration # make sure to build first
$ npm run test # runs all of the above
```
