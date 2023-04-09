# crispy-octo-adventure
function hideResolveAndCancelRibbonButtons() {
// Default return value to false. Hide buttons
var value = false;
// Set variable with Customer Service Manager security role name
var constCSMRole = "Customer Service Manager";
// Get the Current User's Security Role names
var userRoleNames = Xrm.Utility.getGlobalContext().userSettings.roles.getAll();

// loop through roles and look for Customer Service Manager role
for (var i = 0; i < userRoleNames.length; i++) {
if (userRoleNames[i].name === constCSMRole) {
// Hide Resolve button and the Cancel button on Case
value = true;
break;
}
}
return value;
}
