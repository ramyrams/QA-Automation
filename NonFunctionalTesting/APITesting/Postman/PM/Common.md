
When placed in the Postman 'Tests' tab, this script will unset all the variables that start with a specifically given prefix so that it's slightly different from the .clear() built-in fuction.

function cleanup() {
    const clean = _.keys(pm.environment.toObject())
    _.each(clean, (arrItem) => {
        if (arrItem.startsWith("some_prefix")) {
            pm.environment.unset(arrItem)
        }
    })
}
cleanup()



// Check that the date format is correct using .match()
pm.expect(result.dob.date).to.match(/^\d{4}-\d{2}-\d{2}T\d{2}:\d{2}:\d{2}Z$/);


const moment = require('moment');
pm.globals.set("timestamp", moment().format("MM/DD/YYYY"));


const dateNow= new Date();
pm.environment.set('currentDate', dateNow.toISOString());

