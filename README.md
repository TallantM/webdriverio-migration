# WebDriverIO to Cypress/Playwright Migration Demo

A client project demonstration of migrating automated testing from WebDriverIO to Cypress or Playwright, featuring code examples, multi-framework comparisons, and setup instructions for seamless adoption.

## Prerequisites
- Node.js 18.0+
- Git
- Visual Studio Code (with TypeScript extension recommended)
- npm (included with Node.js)

## Setup
1. Clone the repo: `git clone https://github.com/yourusername/webdriverio-migration-demo.git`
2. Navigate to the project: `cd webdriverio-migration-demo`
3. Install dependencies: `npm install`

## Running the Examples Locally
- For Cypress: `npm run cypress`
- For Playwright: `npm run playwright`

## CI/CD
GitHub Actions workflow in `.github/workflows/ci.yml` runs examples on push/pull requests.

## Choose Your Migration Path

| You want...                           | Choose         | Why                                      |
|---------------------------------------|----------------|------------------------------------------|
| Simple setup, great docs, dashboard   | **Cypress**    | Best developer experience                |
| Cross-browser, API testing, mobile    | **Playwright** | Most powerful, Microsoft-backed          |

## The Same Test — Three Implementations

### Original WebDriverIO (before)
```javascript
await browser.url('https://the-internet.herokuapp.com/login');
await browser.$('#username').setValue('tomsmith');
await browser.$('#password').setValue('SuperSecretPassword!');
await browser.$('button[type="submit"]').click();
```

### Migrated to Cypress
```typescript
cy.visit('https://the-internet.herokuapp.com/login');
cy.get('#username').type('tomsmith');
cy.get('#password').type('SuperSecretPassword!');
cy.get('button[type="submit"]').click();
```

### Migrated to Playwright
```typescript
await page.goto('https://the-internet.herokuapp.com/login');
await page.fill('#username', 'tomsmith');
await page.fill('#password', 'SuperSecretPassword!');
await page.click('button[type="submit"]');
```
