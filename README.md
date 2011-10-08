# Description

PresoClicker is a Android app that allows you to use a phone or tablet as a slide deck clicker.

# Getting Started

Before using this application, you must register for an account on http://pusher.com and add your account data to the Pusher.java file.

# Supported HTML5 Slide Decks

deck.js - http://imakewebthings.github.com/deck.js/

# To Use:

Add the following to your HTML5 slide deck.

`<script type="text/javascript">
    // Enable pusher logging - don't include this in production
    Pusher.log = function(message) {
      if (window.console && window.console.log) window.console.log(message);
    };

    // Flash fallback logging - don't include this in production
    WEB_SOCKET_DEBUG = true;

    var pusher = new Pusher('<INSERT KEY>');
    var channel = pusher.subscribe('preso_channel');
    channel.bind('advance_slide', function(data) {
        $.deck("next");
    });
    channel.bind('decrement_slide', function(data) {
        $.deck("prev");
    });
    channel.bind('go_to_slide', function(data) {
        $.deck('go',Number(data.slide));
    });
    channel.bind('menu', function(data) {
    });
  </script>`
  
* Note: depends on a web connection for both devices, cell phone/tablet and computer.