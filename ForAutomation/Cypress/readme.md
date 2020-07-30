--------------------------------------------------------------------------------------------------------------------
# Dev Environment Setup
--------------------------------------------------------------------------------------------------------------------
```batch
Install Node and confirm the version
Install NPM and confirm the version
Install VS Code
npm install cypress --save-dev
npx cypress --version
npm install -g allure-commandline --save-dev
npm i -D @shelex/cypress-allure-plugin
npm install -D cypress-xpath
```
--------------------------------------------------------------------------------------------------------------------
# Test Dev Environment Setup
--------------------------------------------------------------------------------------------------------------------
# Create a new project folder
```batch
MD <Project Folder>
CD <Project Folder>
```

# to generate the  package.json file
npm init -y

--------------------------------------------------------------------------------------------------------------------
# Developement
--------------------------------------------------------------------------------------------------------------------
```batch
/// <reference types="cypress" />

# Skeleton Class
describe(", ()=>{
    before(()=>{
		cy.visit('localhost:3000')
		cy.clearCookies()
    });

    it('', ()=> {
    });
});
```
--------------------------------------------------------------------------------------------------------------------
# Test run during the development 
--------------------------------------------------------------------------------------------------------------------
```batch
npx cypress open
cypress run --record "--parallel" "--group" "4x-electron"


.gitignore file:
	node_modules/
	cypress/videos/
	cypress/screenshots/
```
 
--------------------------------------------------------------------------------------------------------------------
# Execure and generate Allure Report
--------------------------------------------------------------------------------------------------------------------
```batch
npx cypress run --config video=false --env allure=true --browser chrome

parallel execution
	cypress run --record --group 1x-electron
	cypress run --record --group 2x-chrome --parallel --browser chrome
	cypress run --record --group 4x-electron --parallel
	cypress run --record --group Windows/Chrome-69 --browser chrome
	cypress run --record --group Mac/Chrome-70 --browser chrome
	cypress run --record --group Linux/Electron
	cypress run --record --group package/admin --spec 'cypress/integration/packages/admin/**/*'
	cypress run --record --group package/customer --spec 'cypress/integration/packages/customer/**/*'
	cypress run --record --group package/guest --spec 'cypress/integration/packages/guest/**/*'
```



--------------------------------------------------------------------------------------------------------------------
# Allure Reports
--------------------------------------------------------------------------------------------------------------------
```batch
Note: https://github.com/Shelex/cypress-allure-plugin
Example: 
	https://github.com/Shelex/cypress-allure-plugin-example/blob/master/cypress/integration/examples/actions.spec.js
	https://github.com/Ebazhanov/cypress-allure2-report-example
npx cypress run --config video=false --env allure=true --browser chrome
npx allure generate --clean
npx allure open
```



--------------------------------------------------------------------------------------------------------------------
# Cypress Chat group
--------------------------------------------------------------------------------------------------------------------
https://gitter.im/cypress-io/cypress

--------------------------------------------------------------------------------------------------------------------
# Awesome Cypress packages
--------------------------------------------------------------------------------------------------------------------
https://awesomejs.dev/for/cypress/pkg/246063676626305550/releases


--------------------------------------------------------------------------------------------------------------------
# Chrome Extensions
--------------------------------------------------------------------------------------------------------------------
ChroPath
Cypress Recorder
