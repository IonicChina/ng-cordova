---
layout: docs-plugins
title: ngCordova - Document and Examples - by the Ionic Framework Team

plugin-name: $cordovaSMS
source: https://github.com/driftyco/ng-cordova/blob/master/src/plugins/sms.js
official-docs: https://github.com/cordova-sms/cordova-sms-plugin
icon-apple: true
icon-android: true
icon-windows: true
---

Easily send SMS natively in iOS or Android SMS app

```
cordova plugin add https://github.com/cordova-sms/cordova-sms-plugin.git
```


#### Example

```javascript
module.controller('ThisCtrl', function($cordovaSms) {

 document.addEventListener("deviceready", function () {

    $cordovaSms
      .send('phonenumber', 'SMS content', options)
      .then(function() {
        // Success! SMS was sent
      }, function(error) {
        // An error occurred
      });

  });

});
```
