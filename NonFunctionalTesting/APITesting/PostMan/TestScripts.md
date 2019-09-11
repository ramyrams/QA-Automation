
# Global variables

## Setting
//Set a global variable
pm.globals.set('myVariable', MY_VALUE);

##Getting
//Get a global variable
pm.globals.get('myVariable');
pm.variables.get('myVariable');

## Removing
//Clear a global variable
pm.globals.unset('myVariable');

Remove ALL global variables (rather unusual)
pm.globals.clear();

# Variables
var value = pm.variables.get("variable_key");
