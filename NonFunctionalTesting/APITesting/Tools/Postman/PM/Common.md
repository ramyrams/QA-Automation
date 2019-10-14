https://github.com/RobotRogue/postmanScripts/blob/master/getStripeToken.js
https://github.com/RobotRogue/postmanScripts/blob/master/preReqScripts.js
https://github.com/RobotRogue/postmanScripts/tree/master/workflows


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



# How to get to request parameters in Postman?
pm.request.url.getQueryString() // example output: foo=1&bar=2&baz=3

pm.request.url.query.all()

var query = {};
pm.request.url.query.all().forEach((param) => { query[param.key] = param.value});

const paramsString = request.url.split('?')[1];
const eachParamArray = paramsString.split('&');
let params = {};
eachParamArray.forEach((param) => {
    const key = param.split('=')[0];
    const value = param.split('=')[1];
    Object.assign(params, {[key]: value});
});
console.log(params); // this is object with request params as key value pairs



pm.request.headers.add({
    'key': "myvar",
    'value': pm.environment.get("myvar")    
})


pm.sendRequest({
    url: "https://mydomain/ers/config/endpoint",
    method: 'GET',
    header: {
        'content-type': 'application/json',
        'accept': 'application/json',
        //'x-site-code': pm.environment.get("x-site-code")
        'X-CSRF-TOKEN': 'fetch'
    },
    body: {
        mode: 'raw'//,
        raw: JSON.stringify({ email: pm.environment.get("email"), password: pm.environment.get("password") })
    }
}, function (err, res) {

    pm.environment.set("X-CSRF-TOKEN", "Bearer " + res.json().token);
});
