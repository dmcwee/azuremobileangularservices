azuremobileangularservices
==========================

This project provides an AngularJS Service that wraps the Azure Mobile Services. While developing I found issues trying to tie to the Azure Mobile Services especially around where updates were made and the UI would fail to refresh. Over development time I have worked to make this class more generic and to incorporate more advanced Azure Mobile Service features.

===================================
Example
===================================

app.js
-------------------------------------------------------
var myAngularJSApp = angular.module('myAngularApp', [
 'ngRoute',
 'azureServicesModule',
 'otherModule1',
 ...
 ]);

controllerExample1.js
---------------------------------------------------------
myModule.controller('exampleController', ['$scope', '$location', '$routeParams', 'AzureMobileServices',
  function ($scope, $location, $routeParams, AzureMobileServices) {
    $scope.read = function() {
      AzureMobileServices.read("myTable", null) //the second parameter could be a filter like: { name: "john" }
      .then(function(myTableObjs) {
      //process the objects and update your UI
    });
  }
});
