---
layout: docs-plugins
title: ngCordova - Document and Examples - by the Ionic Framework Team

plugin-name: $cordovaNativeAudio
source: https://github.com/driftyco/ng-cordova/blob/master/src/plugins/nativeAudio.js
official-docs: https://github.com/SidneyS/cordova-plugin-nativeaudio
icon-apple: true
icon-android: true
icon-windows: false
---

Cordova / PhoneGap 3.5+ extension for Native Audio playback, aimed at HTML5 gaming and audio applications which require minimum latency, polyphony and concurrency.

```
cordova plugin add https://github.com/SidneyS/cordova-plugin-nativeaudio.git
```

```javascript
module.controller('MyCtrl', function($scope, $cordovaNativeAudio, $timeout) {

  $cordovaNativeAudio
    .preloadSimple('click', 'audio/click.mp3')
    .then(function (msg) {
      console.log(msg);
    }, function (error) {
      alert(error);
    });

  $cordovaNativeAudio
    .preloadComplex('music', 'audio/music.mp3', 1, 1)
    .then(function (msg) {
      console.log(msg);
    }, function (error) {
      console.error(error);
    });

  $scope.play = function () {
    $cordovaNativeAudio.play('click');
    $cordovaNativeAudio.loop('music');

    // stop 'music' loop and unload
    $timeout(function () {
      $cordovaNativeAudio.stop('music');

      $cordovaNativeAudio.unload('click');
      $cordovaNativeAudio.unload('music');
    }, 1000 * 60);
  };

});
```
