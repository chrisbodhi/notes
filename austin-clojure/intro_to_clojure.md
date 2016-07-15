#Starting and an Adventure

_July 11, 2016_
[meetup page](http://www.meetup.com/Austin-Clojure-Meetup/events/231947680/)

##Getting Started with Clojure
Nola Stowe | [slides](http://www.slideshare.net/rubygeek/beginning-clojure-at-austinclojure-meetup)

Start with installing java and leiningen ...or... containers at nitrous.io!

Editors

  - emacs / cider -- with [ParEdit](https://www.emacswiki.org/emacs/ParEdit), [Parinfer](https://shaunlebron.github.io/parinfer) to handle paren matching
  - [nightcode](https://sekao.net/nightcode/) -- rec'd by clojurebridge
  - [cursive](https://cursive-ide.com/)

Practice Coding
  
  - [4clojure.com](4clojure.com) -- in-browser
  - [clojurekoans.com](clojurekoans.com) -- git clone
  - [codewars.com](codewars.com) -- in-browser

How to get halp

  - go to the group's chat: clojurians :slack:
  - http://www.clojure.org
  - http://www.clojuredocs.org
  - in the repl: `(clojure.repl/doc FUNCTION)` and `(clojure.repl/source FUNCTION)`

Books
  
  - [Living Clojure](http://shop.oreilly.com/product/0636920034292.do) -- in the couch-to-5k method
  - [Clojure for the Brave and True](http://www.braveclojure.com) -- what she started with
  - [Clojure Cookbook](https://github.com/clojure-cookbook/clojure-cookbook)
  - [Clojure Applied](https://pragprog.com/book/vmclojeco/clojure-applied) -- her fave for intermediate

Moar

  - [clojuregeek.com/getting-started](clojuregeek.com/getting-started) -- Nola's site
  - [purelyfunctional.tv](purelyfunctional.tv)

Promoting Clojure in Austin

  - There's a Trello board for tasks to complete for the site

* * *

##An Adventure in Serverless ClojureScript
Norman Richards | [slides](http://www.slideshare.net/normanrichards/an-adventure-in-serverless-clojurescript)

###The Original Stack

- Figwheel
- Quiescent with Sablono [instead of Om]
- cljs-ajax
- Bootstrap 4 ["why go beta when you can go alpha"]

###The Project

[http://gateis.red](http://gateis.red)

_there's an emacs meetup?_

figwheel, interacting with browser from emacs

doing a js build, deploy using s3 since it's just a static site with HTML + JS on top
