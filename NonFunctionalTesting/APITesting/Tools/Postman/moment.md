
# moment example
https://momentjs.com/timezone/docs/


// Bringing in the moment module
var moment = require('moment');

// Creating a variable to use as the start date in a particular format
pm.globals.set("startDate", moment().format("DD/MM/YYYY"));

// Creating a variable to use as the end date and using the .add() function to set it 30 days in the future
pm.globals.set("endDate", moment().add(30,'days').format("DD/MM/YYYY"));
