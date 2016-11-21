<html>
<head>
  <title>Angular Practice</title>
  <link rel="stylesheet" type="text/css" href="angular.css">
  <script src="http://ajax.googleapis.com/ajax/libs/angularjs/1.4.8/angular.min.js"></script>
  <script type="text/javascript">
  angular.module('myApp', []).controller('myController', function($scope){
$scope.employees =
[{name : "roy", DOB : "June 25", Gender : "Male", Salary : "30000.32", Country : "USA"},
{name : "randy", DOB : "June 22", Gender : "Male", Salary : "50000.90", Country : "USA"},
{name : "john", DOB : "June 21", Gender : "Male", Salary : "60000.98", Country : "UK"},
{name : "jacky", DOB : "June 27", Gender : "Male", Salary : "70000.76", Country : "Brazil"},
{name : "zoro", DOB : "June 26", Gender : "Male", Salary : "90000.66", Country : "Venezuela"},
 ];
 $scope.test = 5;
 $scope.orderByMe = function(x) {
  $scope.myOrderBy = x;
 }
})
  </script>
</head>
<body>
<div ng-app="myApp" ng-controller="myController">
<input type="number" ng-model="test">
<input type="text" ng-model="find.name">
<input type="text" ng-model="find.Country">
<input type="checkbox" ng-model="exactMatch">
<table border="2">
<tr>
<th ng-click="orderByMe('name')">Name</th>
<th ng-click="orderByMe('DOB')">DOB</th>
<th ng-click="orderByMe('Gender')">GENDER</th>
<th ng-click="orderByMe('Salary')">Salary</th>
<th ng-click="orderByMe('Country')">Country</th>
</tr>
<tr ng-repeat="x in employees | limitTo:test | filter:find:exactMatch">
<td>{{x.name | uppercase}}</td>
<td>{{x.DOB | date}}</td>
<td>{{x.Gender}}</td>
<td>{{x.Salary | currency}}</td>
<td>{{x.Country}}</td>
</tr>
</table>
<input class="doi" type="text" ng-model="find">
</div>
</body>
</html>
