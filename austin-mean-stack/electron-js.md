#ElectronJS
_May 3, 2016_
[Amir Yasin](https://github.com/ayasin)

[meetup page](http://www.meetup.com/Austin-MEAN-Stack-Development/events/230250653/) | [Electron.js official site](http://electron.atom.io/) | [official docs](http://electron.atom.io/docs/v0.37.8/)

###What It Is
- building fully-native-looking apps using web technologies
- Chromium browser with Node backend
- Core of Atom editor, now its own project

###Java tried this, but...
- not how Java promised it, though, which was a "pile of shit"
- Java ran on three platforms, looked bad on all of them
- Can't create a new UI while still feeling native
- integration into the OS must be seamless
- app and install process must be the same as native apps

###Good Things for Electron
- Access to all OS features available to JS
- Packaged in native binary/native-feeling installer
- Lots of folks using it, like :slack:

###Parts of an Electron App
- Chromium _render process_
- Nodejs server _main process_
- interprocess communication between _main_ and _renders_
- Able to have as many render processes, but they don't communicate with each other

- - -

[_Off to look at some code..._](https://github.com/ayasin/electron-color-picker-sample)

`electron-request-response` repo on Github

_main_ process in `index.js`

`app.on('ready', () =>` is event emitted by Electron, where we start adding windows. Listening for other events [`window-all-closed`, `login`], too.

Modules for interacting with OS processes are available for mostly _main_ process, but also some _render_ and both processes.

Wanna keep the _render_ process as light as possible, keep the more intensive or longer stuff in the _main_ process to make sure the app stays responsive to user input. 

- Run your app: `electron .`
- Debug your app's _main process_: `node-inspector` [[repo](https://github.com/node-inspector/node-inspector)], copy URL, open it in Chrome, now run `electron --debug .` in a new terminal
	- Able to now drop in breakpoints in Chrome window
	- Able to also debug using i.e. WebStorm

###Packaging

[`electron-packager`](https://github.com/electron-userland/electron-packager)

Updating can look seamless for platform

Packages Node and Chromium, so no need for user to have Chrome or Node installed

Splitting up frontend and backend stuff, limiting to what's necessary for packaging

Two processes [_main_ and _render_], ergo, two JS entrypoints in our HTML file

Source code is all available in the app directory, though. But "fool's errand" to keep it all away from users [can have app reach out to server to run sekrit code, though]




