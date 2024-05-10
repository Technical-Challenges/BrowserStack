# BrowserStack Technical Challenge

## Tech Challenge

The challenge involved creating a test suite that executes the following actions on BrowserStack:

1. Write a small Selenium test suite that meets the following criteria:

    a. Can be written in any language or framework

    b. Executes on BrowserStack (you will need to create a free trial)

    c. The suite must contain a test doing the following:

        i. Log into www.browserstack.com using your trial credentials
        ii. Assert that the homepage includes a link to Invite Users and retrieve the link’s URL
        iii. Logs out of BrowserStack

    d. Run across the following three browsers in parallel:

      - Windows 10 Chrome
      - macOS Ventura Firefox
      - Samsung Galaxy S22

> **Note:** Sensitive data should not be hardcoded and can be referenced as a variable

2. Execute the test suite from a Jenkins server

3. When complete, please share the suite as a Github repo and provide evidence of your Jenkins job -- either the pipeline code or screenshots of the build configuration.
