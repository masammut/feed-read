# Feed-Read

[![Build Status](https://secure.travis-ci.org/sentientwaffle/feed-read.png?branch=master)](http://travis-ci.org/sentientwaffle/feed-read)

[Node.js](http://nodejs.org/) module for parsing RSS and ATOM feeds into
a common article object.

# Installation

    $ npm install masammut/feed-read

# Usage

    var feed = require("feed-read");

## `feed(url, callback)`
Fetch a feed.

    feed("http://craphound.com/?feed=rss2", function(err, feed, articles) {
      if (err) throw err;
      // Feed:
      //
      //   * "name"
      //   * "source"
      //   * "link"
      //   * "image"
      //          
      // Each article has the following properties:
      // 
      //   * "title"     - The article title (String).
      //   * "author"    - The author's name (String).
      //   * "link"      - The original article link (String).
      //   * "content"   - The HTML content of the article (String).
      //   * "published" - The date that the article was published (Date).
      //   * "media"     - {thumbnail (Attributes as Object), content (Attributes as Object)} - RSS Only for now

      // 
    });

## `feed.rss(rss_string, callback)`
Parse a string of XML as RSS.

The callback receives `(err, articles)`.

## `feed.atom(atom_string, callback)`
Parse a string of XML as ATOM.

The callback receives `(err, articles)`.

## `feed.identify(xml_string)` // => "atom", "rss", or false
Identify what type of feed the XML represents.

Returns `false` when it is neither RSS or ATOM.


# License
See LICENSE.

# To Do
* Test ATOM's feed.image
* Add media to ATOM
* Update test scripts

