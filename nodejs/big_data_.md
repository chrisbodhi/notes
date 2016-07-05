#Big Data with MapReduce
_June 23, 2016_
[Michael Cole](https://bigsmall.io)

##What is Big Data?

- "Magic beans for some sweet marketing"
- ad hoc queries of large data sets in human time scales
- divide and conquer algos <--- MapReduce is a classic one of these
- Everything Hard is a scary basement of Cluttered Simple

##What is MapReduce?

_Interactive portion!!! With notecards and pens!!!_

1. write name of animal on front
2. on back, get rid of unneccessary data [the map]
	- `unicorn` => `u,3,4`
3. shuffle cards to the right
4. sort by first letter
	- helpful because some good algos need a sorted input
5. get total vowels & total words, then avg vowels per word [the reduce]
6. don't need results to come in at the same time

To summarize: `data -> map -> shuffle/sort -> reduce`

node.js: single-threaded, so don't shuffle/sort

data -> datum

<american yodels graphic>

###JS Map and Reduce

```
var data = [...];
var mapped = data.map(callback(datum));
var reduced = mapped.reduce(callback(acc, item), initAcc);
```

`for() loops are for n00bs` <--- called himself out for being judgemental

###MongoDB Map and Reduce

`db.someCollection.mapReduce( map, reduce, { query, out });`

uses sharded collections across many machines, so many single-threaded processes going at once

Map for Mongo: `function() { emit(this._id, this.data.length); };`

_`this._id` is key, `this.data` is doc_

`this` is basically an individual document within the context of this Mongo code

Because map/reduce are being used in-memory, there are restrictions for the size of those temp collections.

_...but then I thought, that'll be hard, so I didn't._


#LoDash

"a modern js utility library"

Shorthand for `map` &mdash; passing in object key's name instead of an entire callback, ex: `_.map(users, 'name');` === `_.map(users, (user) => user.name);`

Bob Holben's lodash presentation [which is "much better"] -- [http://slides.com/bholben/lodash-faves-mar-2016#/](http://slides.com/bholben/lodash-faves-mar-2016#/)

Don't mutate in FP, but there are some places where lodash does just that: `_.pullAll` &mdash; mutates &mdash; vs `_.difference` &mdash; does not mutate

Function chaining: `_.tap` and `_.thru` to get value of array in the middle of the chain; `_.tap` returns, `_.thru` does not

Rather than `[].length` check for deciding what to do, use `_.isEmpty([]); => true`

`_.clone` v `_.cloneDeep` for copying objects

Favorites from the crowd -- `_.get`, `_.debounce` v `_.throttle`

hr

[meetup page](http://www.meetup.com/noders/events/231804730/) | [slides](http://slides.com/michaelcole/deck-1-2#/)
