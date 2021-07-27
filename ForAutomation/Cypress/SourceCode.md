# Run your test multiple times
Cypress._.times(10, () => {

  it('flaky test', () => {

    // test code

  });

});



cy.waitUntilAllAPIFinished();

   cy.get('#xhr-result').should('contain', '"page":1');






cy.title().contains('My App')     // Errors, 'title' does not yield DOM element
cy.getCookies().contains('_key')  // Errors, 'getCookies' does not yield DOM element
cy.get('form').contains('submit the form!').click()

cy.get('form')                  // yields <form>...</form>
  .contains('form', 'Proceed')  // yields <form>...</form>
  .submit()                     // yields <form>...</form>



cy.contains('Log In')

cy.contains('Age').find('input').type('29')

cy.contains(108762).click().contains('Yes, Delete!').click()



cy.setCookie('cookiName', 'someValue');

# Make An Element Visible On The Page
cy.get('.myClass').scrollIntoView();


cy.wait(50);


# Stubbing A Response
cy.route('GET', userSummary, 'fx:responses/user/userSummary\_NonEIP').as('myAlias');
cy.wait(\['@myAlias'\]);


# Disabling Uncaught Exceptions
export function toogleUncaughtException(enabled){
    Cypress.on('uncaught:exception', (err, runnable) => {
        return enabled;
      });
}




//Get me the first instance of '.thething'
cy.get(thething).first
//Get me the third instance of '.thething'
cy.get(thething).eq(2)
//Get me the last instance of '.thething'
cy.get(thething).last




describe('Alt Text Test', () => {
it('should find a particular element, its alt text and check the alt text does not exceed a certain length', function() {
cy.get('.content-wrapper.row-1')
.find('picture')
.find('img')
.first()


it('Visit the app', function () {
    cy.visit('http://localhost:3000')
    cy.wait(3000)
    cy.get('[data-cy="loader"]').should('not.exist');
  }) 
  
  

.should('have.attr', 'alt')
.then(alttext => {
expect(alttext.length).not.to.be.greaterThan(160);
});
// .and('match', /.+/);
});
});
});





it('loads', () => {
  cy.contains('h1', 'todos')
})



  


# How to get the text input field value to a const and log that value in Cypress.io
cy.get('input[name="email"]')
  .invoke('val')
  .then(sometext => cy.log(sometext));
  
#  How to get div 'text' value in Cypress test using jquery
 cy.get(".ibxudA").find('.WildnessText-kRKTej').should('have.text',"Wildnes
cy.contains('Wildness')




cy.get('.mat-paginator')
  .find('.mat-paginator-range-label')
  .should('contain', `20 of ${dataSource.length}`);
  
  
 
cy.route({ method: 'POST', url: '**/graphql', response: manyItems }).as('manyItems');
cy.visit('/items');
cy.wait(['@manyItems'], { requestTimeout: 10000 });


cy.get('.mat-paginator')
  .find('button.mat-paginator-next')
  .click();

 
 cy.get('.s-item').find('.s-item__price').each(($el) => {
    expect(parseFloat($el.text().replace(/\$/g, ''))).to.be.greaterThan(40)
        .but.to.be.lessThan(100);
 )}


# Page Object


          
import LoginPage from "./ObjectModel/LoginPage"

describe('home page', () => {
    it('loginPage', function () {
        const lp = new LoginPage()
    })
}


class LoginPage {
    visit(){
        cy.visit('https://facebook.com');
    }

    fillEmail(value){
        const feild = cy.get('#email')
        feild.clear()
        feild.type(value)
        return this
    }
    
    fillPassword(value){
        const feild = cy.get('#pass')
        feild.clear()
        feild.type(value)
        return this
    }
    
    submit(){
        const button = cy.get('#u_0_b')
        button.click()
    }
}

export default LoginPage;




 cy.get('.s-item').find('.s-item__price').each(($el) => {
    expect(parseFloat($el.text().replace(/\$/g, ''))).to.be.greaterThan(40)
        .but.to.be.lessThan(100);
 )}
 
 
 
 Cypress get specific text
 
 
 cy.get('[for="prod-field"]').should(($el) => {
  expect(
    $el
      .contents() // Grab all contents
      .first() // The text node you're looking for
      .text() // Get the text
      .trim() // And trim the white space
  ).to.eq('Project');
});


<label for="prod-field"
  ><span class="label-text">Project</span>>
  <span class="aui-icon">Required</span>
</label>

cy.get('[for="prod-field"] .label-text').should('have.text', 'Project');




# How to assert if this text contain at least one words from one statement in cypress
Use regular expression
cy.get(".stitle").contains(/(learning|table)/i);


<p class="stitle">
  learning Lorem ipsum, dolor sit amet consectetur adipisicing elit.
  Dolor, in nulla dolores vero autem cum vitae. Eaque ipsum, numquam, ea
  nam iste a quaerat excepturi facilis praesentium repellendus laudantium
  blanditiis.
</p>
 
 
# get child element in cypress

<ul tag-test="tab">
  <li>1</li>
  <li>2</li>
  <li>3</li>        // test should find this one
</ul>

<ul tag-test="another">
  <li>4</li>
  <li>5</li>
  <li>6</li>        // test should ignore this one
</ul>


the test could be

cy.get('ul[tag-test=tab]')
  .find('li:last-child')     // use find here to restrict search to previous subject
  .contains('3')
or to grab the jQuery object

cy.get('ul[tag-test=tab]')
  .find('li:last-child')
  .then($lastLI => {
    expect($lastLI).to.contain(3)
  })
  
  
 # How to find element and select by cypress.io with vue.js v-select?
 <v-select
      label="label"
      v-model="ccRcode"
      ref="ccRcode"
      :items="getData"
      item-text="descWithCode"
      item-value="code"
      value="{ ccRcode }"
      data-cy='select-input'
></v-select>
And then in your test:

cy.get('[data-cy=select-input]').select('optionValue')





# Access a new window - cypress.io

cy.visit('http://localhost:3000', {
  onBeforeLoad(win) {
    cy.stub(win, 'open')
  })
}

// Do the action in your app like cy.get('.open-window-btn').click()

cy.window().its('open').should('be.called')

In a new test, use cy.visit() to go to the url that would have opened in the new window, fill in the fields and click the buttons like you would in a Cypress test.
cy.visit('http://localhost:3000/new-window')



# How to get div 'text' value in Cypress test using jquery
cy.get(".ibxudA").find('.WildnessText-kRKTej').should('have.text',"Wildness")


# how to find by text content?
cy.get('YOUR_BUTTON_CLASS').contains('Customer');




Use testing-library/cypress-testing-library

After the installation, just import it in cypress' commands.js:

import '@testing-library/cypress/add-commands'
And in your tests

cy.findAllByText("Jackie Chan").click();
cy.findByText("Button Text").should("exist");
cy.findByText("Non-existing Button Text").should("not.exist");
cy.findByLabelText("Label text", { timeout: 7000 }).should("exist");
cy.get("form").within(() => {
  cy.findByText("Button Text").should("exist");
});
cy.get("form").then((subject) => {
  cy.findByText("Button Text", { container: subject }).should("exist");
});


https://github.com/testing-library/cypress-testing-library


How will we call a function written in a separate file from a Cypress test?

Put this in your support/commands.js file:

Cypress.Commands.add('subValues', (a, b) => { return a - b });
Put this in your support/index.js file, if it isn't already there (it should be):

import "./commands";
Call it in your test like so:

describe ('Calling a function', function(){
  it('Call the Subtract function and asert the calculation', function(){
    cy
      .subValues(15, 8)
      .should('eq', 7) // true        
    });
});


# Checking radio buttons in Cypress

cy.get('[type="radio"].XyzTypeRadio').check("2")

cy.get('[type="radio"].XyzTypeRadio').first().check()


# Debugging Cypress tests in Visual Studio Code


# Anyway to test for specific scroll amount?
cy.window().then(($window) => {
  expect($window.scrollY).to.be.closeTo(400, 100);
});


#How can I use cypress to assert that an image is the correct one?
cy.visit(URL);
cy.get('your_selector').should('have.attr', 'href', '/your_picture_href')


# How can I check URL content with cypress
const path = 'user/survey';

cy.url().then(($url) => {
    if($url.includes(path)) {
        cy.log("Yes")
    } else  {
        cy.log("No")
      }
})


# How to test file inputs with Cypress?
it('Testing picture uploading', () => {
    cy.fixture('testPicture.png').then(fileContent => {
        cy.get('input[type="file"]').attachFile({
            fileContent: fileContent.toString(),
            fileName: 'testPicture.png',
            mimeType: 'image/png'
        });
    });
});


# Extract text and number from variable

Markup:

<div class="date">Tue 7 Jul</div>

Test:

cy.get('.date').then(($el) => {
    cy.log('original: ' + $el.text());
    const dateString = Cypress.moment($el.text(), 'ddd D MMM')
    const month = Cypress.moment(dateString, 'ddd D MMM').format('MMMM');
    const day = Cypress.moment(dateString, 'ddd D MMM').format('D');

    cy.log(`After formatting month = ${month}`);
    cy.log(`After formatting day = ${day}`);
    expect(month).to.equal('July');
    expect(day).to.equal('7');
});


# What is the difference between cy.readFile and cy.fixture in Cypress.io?
cy.readFile('path/to/test.png', 'base64').then(text => {
    console.log(text); // Outputs a base64 string to the console
});

cy.fixture('path/to/test.png', 'base64').then(text => {
    console.log(text); // Outputs the same base64 string to the console
});

# How to check if element exists using Cypress.io

    cy.get("body").then($body => {
        if ($body.find("button[data-cy=appDrawerOpener]").length > 0) {   //evaluates as true
            cy.get("button[data-cy=appDrawerOpener]")
            .click();
        }
    
----------------------------
function setup() {
  cy.wrap(app.clearDatabase()).then(() => console.log('got to 1'));
  cy.wrap(app.makeDatabase()).then(() => console.log('got to 2'));
}
beforeEach(() => {
  setup();
  cy.visit('/');
});
--------------------------	

// This is where I overwrite all of the console methods.
    ['log', 'info', 'error', 'warn', 'debug'].forEach((consoleProperty) => {
      appWindow.console[consoleProperty] = function (...args) {
	  
	  };
	
Last page Scanned : https://stackoverflow.com/questions/tagged/cypress?tab=active&page=10&pagesize=50




https://github.com/Shelex/cypress-allure-plugin

@ Sample Code
https://github.com/cypress-io/testing-workshop-cypress
https://github.com/cypress-io/testing-workshop-cypress/tree/master/cypress/integration
https://github.com/cypress-io/cypress-realworld-app/blob/develop/src/__tests__/bankaccounts.test.ts
https://github.com/dobromir-hristov/cypress-e2e-testing-examples






