
CookiePolicy
============

A jQuery plugin to implement an EU implied cookie consent message box. This plugin is not designed to control the inclusion 
of 3rd party JavaScript - it simply provides a mechanism to dismiss the cookie policy message.

Installation
------------

To install the CookiePolicy jQuery plugin, simply download and extract to a public location. Then, include the JavaScript and CSS file like so:

	<link href="cookiepolicy/cookiepolicy.jquery.css" media="screen" rel="stylesheet" type="text/css" />
	<script src="cookiepolicy/cookiepolicy.jquery.js"></script>

Usage
-----

The CookiePolicy plugin works by appending the HTML for the message box to an element you select (usually the 'body' tag). For basic usage, please do the following:

```html
<script>
    (function($) {
        $('body').cookiepolicy();
    })(jQuery);
</script>
```

You can also pass several options to CookiePolicy:

```html
<script>
    (function($) {
        $('body').cookiepolicy({
            message: 'This is overriding the message. It's also tokenised, so you can pass other options to the message, such as your <a href="%cookie_policy_url%">cookie policy</a> link URL.'
            , cookie_policy_url: 'http://www.example.com/cookie-policy.html'
            , extra_class: 'cookiepolicy-message-box' // Append an extra class to the message box wrapper
            , close_button_text: 'Close' // The text rendered within the close <button> of the message box
            , close_button_title: 'Close this message box' // Text passed to the title attribute of the close <button>
            , cookie_name: 'cookie_policy_messagebox' // The name of the cookie set to track the closure of the message box (Remember to add this to your cookie policy!)
            , cookie_expire_days: 10 // The number of days CookiePolicy will track the closure of the message box
            , on_open: function() {
                // Callback that runs when the message box is open
            }
            , on_close: function() {
                // Callback that runs when the message box is closed (When the close event is triggered)
            }
            , on_closed: function() {
                // Callback that runs when the message box is closed (When close event has been previously triggered)
            }
        });
    })(jQuery);
</script>
```
