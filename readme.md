# Cypress — ParaBank business workflows

Web automation practice against **ParaBank**, using Cypress with JavaScript specs, TypeScript page objects and business keywords, CSV fixtures, and Mochawesome HTML reporting.

## Scenarios

- Log in and log out using a JSON fixture.
- Open accounts using CSV rows.
- Transfer funds between demo accounts.
- Combine account creation and a transfer in a business workflow.

## Structure

| Location | Responsibility |
| --- | --- |
| [cypress/e2e/e2e.cy.js](cypress/e2e/e2e.cy.js) | Account creation and transfer examples |
| [cypress/e2e/workflows.cy.js](cypress/e2e/workflows.cy.js) | Combined business workflow |
| [cypress/e2e/keywords](cypress/e2e/keywords) | Business actions |
| [cypress/e2e/pages](cypress/e2e/pages) | Page objects, interactions, and report context |
| [cypress/fixtures](cypress/fixtures) | Login JSON and account CSV |
| [cypress.config.js](cypress.config.js) | E2E and Mochawesome reporter configuration |

## Setup

The original project uses Node.js **20.11**. Dependencies include Cypress **13.6.0**, TypeScript **5.3.2**, Papa Parse **5.4.1**, and cypress-mochawesome-reporter **3.8.1** version ranges.

```bash
git clone https://github.com/angel-valdezzz/cypress-web-e2e-demo1.git
cd cypress-web-e2e-demo1
npm install
```

## Run

Open the interactive runner:

```bash
npm run cypress:open
```

Run from the command line with a visible browser (the existing script includes `--headed`):

```bash
npm run cypress:run
```

For a headless run or a specific suite:

```bash
npx cypress run
npx cypress run --spec cypress/e2e/workflows.cy.js
```

## Fixtures and reports

Update [login.json](cypress/fixtures/login.json) for the demo URL and sample user. [account.csv](cypress/fixtures/account.csv) supplies account types and reference IDs. Specs also contain fixed transfer account IDs; check these against the available ParaBank accounts before executing.

CSV rows are iterated inside a single Cypress test, rather than registered as separate tests. The reporter is configured with charts, embedded screenshots, and inline assets. Inspect the report location printed by the runner after execution.

The public demo can reset or change state. Account creation and transfers depend on that state; keep fixtures limited to demo data.

## Related projects

- [Playwright Python example](https://github.com/angel-valdezzz/playwright-python-example)
- [Robot Framework Selenium example](https://github.com/angel-valdezzz/robot-framework-selenium-testing)
- [Portfolio map](https://github.com/angel-valdezzz/angel-valdezzz/blob/main/PORTFOLIO.md)
