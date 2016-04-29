#Microservices: Pros and Cons, Things to Think About
* * *
_April 27, 2016_ Panel discussion

###Definition
- Small software that does one thing well
- Balloon that's half full&mdash;squeeze it and part of it will pop out&mdash;trading complexity, not getting rid of it
- Each microservice has its own datastore that it handles from end to end


###Why Not?
- Coding is easy part, but orchestration, maintenance, and deployment of loosely-coupled system is tough
- Dev ops and devs are siloed
- Lots of jr/assoc devs who need to level up to understand extra complexity
- "It's like herding fleas."
- Lots of crust around deployment
	- Dev ops gets complicated due to distributed architecture around deployment


###How big should a microservice be?
- Small enough to fit full context in yr head
- Big enough to solve a problem
- Owned by one team

###Complexity
- Easy to reuse the train tracks
- As base complexity increases, productivity drops as the app gets bigger

###MVP
- Continuous Deployment / Continuous Integration pipeline, build & test before deployment to production
- "Otherwise, you're doomed."
- Keeping it simple, make sure your deployment is a "non-event".
- Test environment

- - -

_AUTOMATE EVERYTHING_

- - -

- Devs on call for stuff breaking in production --> has led to a jump in code quality because no one wants to get paged at 3am

###Containers
- Removes "works on my box" problems, no more "servers as pets"
- "Nothing so disruptive for our industry as container technology."
- "Paradigm shift"

###Self-Healing

>Plan for failure first

###System Health

>Visualize everything

- [Measure anything, measure everything](https://codeascraft.com/2011/02/15/measure-anything-measure-everything)
- [Hystrix](https://github.com/Netflix/Hystrix)

- - -

[meetup page](http://www.meetup.com/bleeding-edge-web/events/230173731)
|
[april meetup slides](https://edgeatx.github.io/slides/2016/04-apr)
|
[panel slides](http://www.slideshare.net/asiemer/microservices-prosandconsdark)
