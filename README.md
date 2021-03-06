# newrelic-angular

[![Build Status](https://travis-ci.org/prestonvanloon/newrelic-angular.svg)](https://travis-ci.org/prestonvanloon/newrelic-angular)
[![npm version](https://badge.fury.io/js/newrelic-angular.svg)](http://badge.fury.io/js/newrelic-angular)
[![Bower version](https://badge.fury.io/bo/newrelic-angular.svg)](http://badge.fury.io/bo/newrelic-angular)
[![Coverage Status](https://coveralls.io/repos/github/prestonvanloon/newrelic-angular/badge.svg?branch=master)](https://coveralls.io/github/prestonvanloon/newrelic-angular?branch=master)

A module to make reporting with New Relic Browser Insights easier for Angular!

### Features

* Report errors to New Relic with $log! ```$log.error('something really bad happened!');```
* Reports unhandled exceptions to New Relic (thanks to ```$errorHander```)
* Virtual page views (via [angulartics](https://github.com/luisfarzati/angulartics))

### How to

Get it from npm

``` npm install --save newrelic-angular ```

Get it from bower

``` bower install --save newrelic-angular ```

Include the module in your application

```javascript
angular.module('myApp', ['newrelic-angular']);
```

And add ```newrelic-angular.min.js``` to your project.

(Optional) Ignore certain statuses

```javascript
angular.module('myApp', ['newrelic-angular'])
  .config(function(httpInterceptorProvider) {
   httpInterceptorProvider.setStatusesToIgnore([-1, 418]);
  });
```

### Why?

For the sake of reporting! Also, angular's exception handler catches unhandled exceptions and delegates them to $log.error. That's a problem for New Relic because they are also catching unhandled exceptions and thanks to Angular, there aren't any true unhandled exceptions!



License
----

MIT
