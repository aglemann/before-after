before-after
==============

CSS `:before` and `:after` pseudo selectors are really great for things like icons, decorative arrows, etc. If you really need support for these selectors in IE7 this is a drop-in fix.


Why
--------------

There doesn't seem to be a good drop-in patch for `:before` and `:after` anywhere on the web. Dean Edward's [ie7-js](http://code.google.com/p/ie7-js/) does an excellent job of adding this, but also adds a lot of other patches that impact performance and often have undesired effects on the rendering of a page.

This is nothing more than a custom build of *ie7-js 2.1 beta4* using the included `build.php?ie8` (ie8 compat) with the following modules disabled:

* include('ie7-layout.js');
* include('ie7-graphics.js');
* include('ie7-fixed.js');
* include('ie7-overflow.js');
* include('ie7-quirks.js');
* include('ie8-layout.js');
* include('ie8-graphics.js');


Credits
--------------

Absolutely all credit goes to the brilliant [Dean Edwards](http://dean.edwards.name/) and his [ie7-js](http://code.google.com/p/ie7-js/).


Usage
--------------

This will patch in `:before` and `:after` support for IE7. Use like so:

	<!--[if lt IE 8]>
	<script src="path/to/ie8.min.js"></script>
	<![endif]-->

Exact placement in the document shouldn't matter since it attaches to the `onload` event.