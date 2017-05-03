---
layout: post
title: BlocJams
feature-img: "img/sample_feature_img.png"
thumbnail-path: "img/blocJamsLanding.PNG"
short-description: A web app for playing music

---

// Case - Study Draft/Outline //

## _Learning to code_

**BlocJams** was the first major project I was tasked with during my studies in web development at Bloc. The goal of this project was to make a fully functionally music player which consisted of
a landing/home page, a page displaying all avaliable albums to play, and the music player itself; all while still learning how to code.  BlocJams was written in vanilla javascript which was later
refactored using jQuery.  After that app was complete, I recreated the entire app in AngularJS while at the same time learning the fundamentals of the AngularJS framework.

> BlocJams jQuery can be viewed live here: [blocJamsJQuery](http://surveyor-assistance-72210.netlify.com.)

One of the highlights of this project, was seeing the capabilities of both libraries and frameworks.

When we take a look at excerpts from my ``album.js`` file from bloc-jams using jQuery, there is a cavalcade of functions and over 315 lines of code. In this app, this is one of only four script files, and by far the longest.
{% highlight javascript %}
var setSong = function (songNumber) {
    if (currentSoundFile) {
        currentSoundFile.stop();
    }
    currentlyPlayingSongNumber = parseInt(songNumber);
    currentSongFromAlbum = currentAlbum.songs[songNumber - 1];
    //#1
    currentSoundFile = new buzz.sound(currentSongFromAlbum.audioUrl, {
        //#2
        formats: [ 'mp3' ],
        preload: true
    });
    setVolume(currentVolume);
  };

 var seek = function(time) {
     if (currentSoundFile) {
         currentSoundFile.setTime(time);
     }
 }

var setVolume = function(volume) {
     if (currentSoundFile) {
         currentSoundFile.setVolume(volume);
     }
 };
{% endhighlight %}

> An example of a few functions from bloc-jams Jquery.

What is perhaps more interesting to me is how much this page controls essentially everything that the album page and music player does.  

When using AngularJS, not only do we end up writing less code, but it gets broken up more, and structured in my opinion in a much more organized way.  We have a set of controllers, directives, services, and filters that are all individual ``.js`` files. These all communicate to the app itself through the angular module.

// Insert some specific examples comparing the same functionality in Javascript / jQuery / AngularJS.

This project has been a wonderful way for me to jump head first into Javascript, jQuery, and AngularJS.  What I learned here will set a solid foundation, and has given me a solid foundation of knowledge to build apps from in the future.
