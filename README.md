Jaded Bootstrap
---------------

Jade is a very cool templating engine that is included in node.js, with concepts like meaningful spacing and very minor programability [http://jade-lang.com/]

Twitter Bootstrap is an awesome tool for those of us who put together lots of demos at work.

However, it's hard to get excited about wading through a morass of div tags when you are just trying to get a site done.

Sure, Webstorm and Vim are great about helping you find missing div closures, but shouldn't the computer be doing all of that anyway?

Jaded Bootstrap gives you a set of Jade templates that you can use and re-use in your Bootstrap 3+ projects.  Just import it and go!

Usage Cases
-----------

- Setup Internet Explorer Handling.

    doctype html
    head
        ..
        include jaded_bootstrap/mixins/ie.jade
        ...
        +ie('if lt IE 8')
            script(src="https://oss.maxcdn.com/libs/html5shiv/3.7.0/html5shiv.js")
            script(src="https://oss.maxcdn.com/libs/respond.js/1.3.0/respond.min.js")

- Build a Loading-screen modal

    head
        include mixins/bootstrap.jade
        ..
    body
        ..
        +loading-modal("Loading Data")#IdForModal.class_for_modal
        ..



- Build a complex form
_This takes advantage of Jade's ability to abstract operations so you can concentrate on positioning your content (which is what bootstrap is great at)_

    head
        include mixins/bootstrap.jade
        ..
    body
        ..
        .row
            .col-xs-2
                +numericinput("大人", "1")#travellers_adult
            .col-xs-2
                +numericinput("子供", "0")#travellers_children
            .col-xs-3
                +numericinput("赤ちゃん", "0")#travellers_infants
            .col-xs-5
                +dropdown("席種類").trip_type#trip_type
                    option(value="economy") エコノミー
                    option(value="business") ビジネス
                    option(value="first") ファスト


License
-------
The MIT License (MIT)

Copyright (c) 2014 Jawaad Bin Mahmood

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.

