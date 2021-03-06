# Angular Nebri

The simple and easy-to-use package for making Nebri api requests from a Angular application.

This app is intended for use with a Nebri instance. Visit https://nebrios.com to sign up for free!

<h2>Installation</h2>
Copy nebri-angular.js to the appropriate location in your application.
The location should be added to the index or base html page.
```
<script src="/path/to/nebri-angular.js"></script>
```

<h2>Setup</h2>
In app.js, `nebriAngular` should be added to your dependencies.
The config section should be updated as well to include your Nebri instance name.
```
angular.module('myApp', [
  ...,
  'nebriAngular'
]).
config([..., 'nebriAngularProvider', function(..., nebriAngularProvider) {
  ...
  nebriAngularProvider.setInstanceName(your_instance_name);
}]);
```
- instance name is your Nebri instance name. i.e. https://<strong>instance_name</strong>.nebrios.com

<h2>Public Functions</h2>
<strong>api_request</strong>:
- api_module: the name of the api module stored on your Nebri instance
- view_name: the name of the target function contained in the given api module
- method: the desired HTTP request method
- payload: an object containing params and values, can be an empty object

<h2>Usage Example</h2>
<strong>NOTE</strong>: in order to use this app in a controller, you must include `nebriAngular`.
```
nebriAngular.api_request('greeting_api', 'start_greeting', 'get', {"greeting": "hello"})
    .success(function(data){
        console.log(data);
    }).error(function(err){
        console.log(err);
    });
```
