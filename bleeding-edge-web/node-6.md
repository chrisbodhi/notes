#All About Node 6
* * *

Evan Lucas | [github](https://github.com/evanlucas) | [twitter](https://twitter.com/evanhlucas) | [slides](http://evanlucas.com/slides/all_about_node_6.html#all-about-node-6) for this talk


_May 25, 2016_ 
* * *

- Node v7 out in October at the earliest

- Block scoping now works in `sloppy mode`

- Lots breaking changes in the move from v5 to v6:

	- deprecated `new Buffer()` constructor
	- renamed `Worker#suicide`
	- `querystring.parse()` object output no longer inherits from Object.prototype

- Evan's first PR for Node was open for 18 months
	- _there's a lesson about persistence in there_ 

- `./node benchmark/compare.js ./node6 ./node5 -- misc startup`
	- benchmark directory in node directory
	- reference: [benchmarking.nodejs.com](http://benchmarking.nodejs.com)

####Links
[v8-inspector](https://github.com/nodejs/node/pull/6792/)

Get started with contributing with this [post on Medium](https://medium.com/@Trott/a-quick-guide-to-reading-node-js-core-source-c968d83e4194)

* * *

##News

_[link to slides!](https://edgeatx.github.io/slides/2016/05-may/)_

####Chrome v51

- Credential Management API
- Skipping rendering of offscreen x-origin, offscreen reqs
- &c.

####Edge 14 (14342)

- New APIs: web notifications, beacon, fetch
	- beacon: async data posting, like for analytics
- Added es2015/6/7 stuff [lolwut]
- Support WOFF 2.0 [open font biz]

####Safari Tech Preview 5
- [Get it here](https://developer.apple.com/safari/technology-preview/)
- WebKit now at 100% ES2015 coverage :100:

####Babel
- Now compiles Babel 6 using Babel 6
	- Yo dawg, &c.
- Updated `core` and `lodash`

####Angular 2
- 17 beta versions have been released!
- It's a heavy rewrite of Angular 1.

####And...
- NativeScript 2.0 is out for building JS mobile apps
- Electron 1.0 is out for desktop apps
- jQuery 3.0 (RC) is out

_so many cool toys_

* * *

`nvm-windows` -- written in Go -- learn more about it [here](https://github.com/coreybutler/nvm-windows)