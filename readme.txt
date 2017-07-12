=== Detector ===
Contributors: steve.barnett
Tags: detector, device, modernizr
Stable tag: 0.9.5
Requires at least: 3.0
Tested up to: 3.0
License: GPLv2 or later

A WordPress Plugin wrapper for Dave Olsen's Detector: a simple, PHP- and JavaScript-based browser- and feature-detection library.

== Description ==

[Detector](http://detector.dmolsen.com/) is a simple, PHP- and JavaScript-based browser- and feature-detection library that can adapt to new devices & browsers on its own without the need to pull from a central database of browser information.

Also available on GitHub: [https://github.com/SteveBarnett/Detector](https://github.com/SteveBarnett/Detector).

Full documentation is available at [github / dmolsen / Detector](https://github.com/dmolsen/Detector/).

== Installation ==

1. Go to Plugins > Add New, Upload and choose detector.zip.
2. Activate the plugin.

== Frequently Asked Questions ==

= How do I use Detector? =

In order to access the features you need to use the `$ua` object that is automatically created with the inclusion of Detector in your application. Use the `$ua` object in a similar way that you would have used the `Modernizr` object on the client-side:

	global $ua;

	// your script

	if ($ua->svg) {
	    ...
	} elseif ($ua->canvas) {
	    ...
	}

See the [full list of browser features](http://detector.dmolsen.com/demo/modernizr-listing/) that are tested by Modernizr and available with Detector. All of the features tested with [ua-parser-php](https://github.com/dmolsen/ua-parser-php) are also available from the `$ua` variable (e.g. `$ua->isMobile` or `$ua->browserFull`)

Some features, (in particular `video`, `audio`, `input`, and `inputtypes`) have sub-features, so these are available as nested PHP objects:

	if ($ua->inputtypes->search) {
	    print "<input type='search' ...";
	} else {
	    print "<input type='text' ...";
	}

All features are returned as integer `1` or `0` for `true` or `false`, so they can be used in logical evaluations in PHP. Sub-features can return `1`, `0`, or a real value (e.g. screen width).


== To Do ==

* Add some useful responsive image handling, in the style of [picturefill.js](https://github.com/scottjehl/picturefill/). Based on families at first?
* Add functions for conditional loading of content via JS, depending on screen size.
* wp_enqueue_script for Modernizr
* Check Modernizr version, custom
* Add option to add own [feature tests](https://github.com/dmolsen/Detector/wiki/Detector-Test-Tutorial) from admin area?
* Add option to add own [families](https://github.com/dmolsen/Detector/wiki/Detector-Family-Tutorial) from admin area?
* Add shortcodes?


== Changelog ==

= 0.9.5 =

Updated to match dmoslen's current Detector

= 0.8.5 =

Updated to match dmoslen's current Detector

= 0.8.2 =

Updated to match dmoslen's current Detector

= 0.8.1 =

* Initial release. [regexes.yaml from 2012/07/12: 303c8f9](https://github.com/tobie/ua-parser/commit/303c8f905aa34110467cdfe730cf066ae6f6e18e#regexes.yaml)