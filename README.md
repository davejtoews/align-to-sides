# Stick To Sides

This library can be used to dynamically ensure all child elements of a given CSS selector are text aligned according to their position relative to their parent. On page-load the elements' positions are measured, elements nearest the left edge of thier parent are text-aligned left, elements nearest the right edge of their parent are text-aligned right, and if a tolerance value is provided elements further than the tolerance value from either edge are text-aligned center. On a window resize (or orientation change on mobile) the positions are measured again and the text-alignments reset to accomodate any shift in layout caused by the change in window size.

Additional triggers can be added via [LayoutQueue](https://github.com/davejtoews/layout-queue).

##  Installation

Install via npm or yarn.

    npm install stick-to-sides

OR

	yarn add stick-to-sides

Then require this module within your javascript:

    var StickToSides = require('../StickToSides.js');

## Basic Use

The methods of StickToSides all use standard CSS selectors, (e.g. 'p', '.class', '#id'). To align the children of a element or set of elements, pass the selector to `init()`:

    StickToSides.init(selector);

A tolerance value in pixels can be added as a second parameter to set any child elements to `text-align: center;` if they are further than the given pixel value from either side. Without a tolerance value, all children will be text-aligned either right or left.

    StickToSides.init(selector, tolerance);

## Advanced use

To manually unset the text alignment of an elements children use `unset()`:

	StickToSides.unset(selector);

To manually set the text alignment of an elements children use 'set()';

    StickToSides.set(selector);

To add additional triggers for the execution of the queue see the documentation for [LayoutQueue](https://github.com/davejtoews/layout-queue);