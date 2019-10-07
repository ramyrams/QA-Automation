
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
