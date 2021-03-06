---
layout: docs-plugins
title: ngCordova - Document and Examples - by the Ionic Framework Team

plugin-name: $cordovaBackgroundGeolocation
source: https://github.com/driftyco/ng-cordova/blob/master/src/plugins/backgroundGeolocation.js
official-docs: https://github.com/christocracy/cordova-plugin-background-geolocation
icon-apple: true
icon-android: true
icon-windows: false
---

Cross-platform background geolocation for Cordova / PhoneGap with battery-saving "circular region monitoring" and "stop detection".

```bash
cordova plugin add https://github.com/christocracy/cordova-plugin-background-geolocation.git
```

```javascript

module.controller('MyCtrl', function($scope, $cordovaBackgroundGeolocation) {

  var options = {
    // https://github.com/christocracy/cordova-plugin-background-geolocation#config
  };

  document.addEventListener("deviceready", function () {

    // `configure` calls `start` internally
    $cordovaBackgroundGeolocation.configure(options)
    .then(
      null, // Background never resolves
      function (err) { // error callback
        console.error(err);
      },
      function (location) { // notify callback
        console.log(location);
      });


    $scope.stopBackgroundGeolocation = function () {
      $cordovaBackgroundGeolocation.stop();
    };

  }, false);
});
```
