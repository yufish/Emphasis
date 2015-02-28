Prologue
========

Emphasis, with patient help, has moved from its dependency on PrototypeJS to jQuery.

Emphasis
========

Emphasis provides dynamic paragraph-specific anchor links and the ability to highlight text in a document,
all of which is made available in the URL hash so it can be emailed, bookmarked, or shared.

For more information and examples please go to this blog post:

http://open.blogs.nytimes.com/2011/01/11/emphasis-update-and-source/

The latest version of Emphasis no longer requires jQuery.

Configuration
-------------

The main configuration element is specifying what paragraph elements are in scope and are not. To this end
we specify the elements on or near Line 54:

    this.paraSelctors = document.querySelectorAll('#article p');

This covers a lot of common markup in many sites and blog. However this could be configured for your specific site.

Example: If all your P tags reside in DIV tags with the "entry" classname, then this would be sufficient:

    this.paraSelctors = document.querySelectorAll(".entry p:not(p[class]):not(:empty)");

Over at The New York Times, we'd use the following:

    this.paraSelctors = document.querySelectorAll('.articleBody p:not(p[class]):not(:empty)', '#articleBody p:not(p[class]):not(:empty)', '#content div.entry-content p:not(p[class]):not(:empty)');

Usage
-----

Once up and running, a reader can double tap the SHIFT key to show the Paragraph links.
Once in this mode they can toggle links and highlighting on a sentence level


Thanks
------

Levenshtein calculation in the script is based on some nice code by Andrew Hedges
http://andrew.hedges.name/experiments/levenshtein/

To-Do
-----

 - Further work on UI for highlighting with focus on simplicity
 - Social
 - Support for touch-based devices
