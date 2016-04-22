#Architecting Node apps at a startup
_April 21, 2016_
[Wes Todd](https://github.com/wesleytodd)

>Move fast and break things

- Mistakes, we all make them. 
- The key is architecting your app to get yourself out of the problems you created. 

##Architectures

### Monoliths

stream.me started with two giant monoliths, then pivoted to SOA...

### Service Oriented Architecture

	1. Explicit boundaries
	2. Autonomous services
		- run in prod as single process
	3. Share schema and contract, not class
		- code not shared across boundaries
	4. Service compatibility is based on policy
		- ex: breaking api change gets a /v2/

	_Lessons Learned_ 

		- Everything getting dumped into giant `modules` directory, not isolating concerns

	_Benefits_

		- New tech easily added
			- Able to add, say, react.js to one app at a time
		- Don't have to test every application when making updates to packages
		- Service outages don't take out the whole application
			- DDoS on chat only brought down chat, not anything else
		- Easy to scale per service, as needed
		- Changes can be rolled out slowly and safely

	~_Source Control_~ _Git_

		- Multiple repos
			- Used to have three, but "it was a paaaain"
		- Single repo
			- Which is what they use
			- Makes deployment and code review easier
			- ~90 services
			- But merges suck and the repo gets big
			- Makes it easy to break Rule #3 and `require` something one should not

### Packages

- Share code across services with packages
- But it can go wrong: `require('../../../../../modules/log');`
- Fix: symlinking local modules directory to node_modules &mdash; `require(log);`
	- But now sharing npm's namespace, so added arbitrary namespacing with `v-`: `require(v-log);`
- Next fix attempt: file-based installs &mdash; _[link to docs](https://nodejs.org/api/modules.html#modules_folders_as_modules)_
	- But then .gitignore'd `node_modules` so sucky dev process when updating local modules
	- Tried to use [linklocal](https://www.npmjs.com/package/linklocal)
- Real fix: using npm
	- Can't open source their code
	- Tried [sinopia](https://www.npmjs.com/package/sinopia)
	- Run your own npm clone
		- `/giphy nope`
	- [Private NPM from NPM](https://www.npmjs.com/npm/private-packages) -- with all of npm's niceties
		- Also set up namespacing
		- Caches modules, private or public
		- Shrinkwrap, too, because it's cool

##### Package Lifecycle

	1. Starts in the application where it's needed...
	2. ...then move it to a shared packaged directory when needed somewhere else...
	3. ...then move it to internal NPM when it's used everywhere and/or it's mature.
		- Try to add tests around this point
	4. Still able to publish as open source

### Environment Dependencies

- configs, other API layers

myslq and redis and nginx and Cassandra and elasticsearch and consul and circus and ....

_Limiting the Baggage_

- Automation [Salt, Vagrant, and Jenkins]
- Use third-party services, especially for development environment [Mandrill, Google Cloud Storage]
- Proxy to remote data stores and APIs [like Redis and Cassandra and &c.]
	- [Example of config tool](https://github.com/MusicMapIo/json-http-proxy) for getting services running on development box

_Dev vs Prod Configs_

- Every app has an index.js as the main entrypoint, but only for dev
	- `var main = module.exports = function(){}; if (require.main === module) {}` to determine if index.js is getting run directly
- [vim as ide]
- Production doing `bin/app`
	- has all of the production-specific biz and setup
	- [runnable](https://github.com/wesleytodd/runnable)
