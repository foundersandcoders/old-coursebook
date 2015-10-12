# Week 5: Build a Redis, Socket.io voting application

Good morning, incipient captains of industry! It is time to carve yourself a bit of that delicious IPO pie.

This week you will be building a ~~clone of~~ competitor to StackOverflow. A FACOverflow, if you will. And, because competition is the core of the tech industry, you will also be clearly documenting your tech stack so that other copycats can follow along in your wake.

Unfortunately, some people without the **visionary brilliance** of you and your team have stolen your idea to steal StackOverflow's idea and are starting on their own FACOverflows. But you can rise above the rabble by refusing to use `for loops`. Your secret weapon: array methods and full test coverage! Also -- you can prove your superiority by breaking their sites (and then teaching them how you did it and how to fix it --- after a period of gloating).

One more thing --- matron wants to see *presentable* repos this week. Bed inspections are at 8. So shine up your folder structure, fold away your messy indentation and mop up your WET code.

To summarise: you should have a realtime-updating list of questions submitted by authenticated users on the homepage of your app. Where you go from there is up to you. But remember, it takes a killing to make a killing ...

## Core Aims
### Some form of authentication
You can choose between cookies and JWTs; between 3rd party authentication and doing it yourself. Here are some pointers:
- A simple(ish) and solid 3rd party authentication is [provided by github](https://developer.github.com/v3/oauth/#web-application-flow)
- You might learn more by doing authentication yourself -- for example with bcrypt
- Cookies may be the simplest option, but JWTs are the future. Your startup has limited energy -- prioritise

### Realtime updates
**Refreshing is cheating**. These should be true realtime updates courtesy of socket.io. The more realtime features you have, the *real*er your chance of making it to the big *time*. **This will be a good opportunity to clarify the connection / distinction between the client and the server**. Thing carefully about your UX here -- the classroom is an endless source of testing guinea pigs.

### Storing questions in a database
You don't *have* to use redis ... I don't care ... No, I'm not crying, go home!

### Your README should be a tutorial that others can follow
It ain't science without replication and you ain't gonna get many public speaking gigs without github stars! Teach your way to the top! :sunrise_over_mountains:
### Aim for full coverage -- you might not get there, but justify in your READMEs anywhere your tests do not cover

https://www.youtube.com/watch?v=Wcze7EGorOk

#### An Extract From A Play
Redis: Travis loves me, Travis loves me not. Travis loves me, Travis loves me not ...
#### TBC!!!!!!!!!!!:rocket:
### No `for loops` unless you can justify them (you can't)
### Break your competitors' sites (only if you know how to fix it!)
### Have a presentable repo


## Additional Features
- Standing out from the crowd is the only way to stand out from the crowd. Pick some extra features to work on (like one or two, don't try and do all of them):
- Up and down voting
- Sort by score
- Tags
- Other sorting options (new, hot, etc.)
- Usernames
- Make old posts fall away
- Deletion only by creator
- Moderators
- Decide who can edit -- is your site like a wiki or like hackernews?
- What defences do you have against jerks?
- Comments / answers
- Be the hottest site on the block :fire:

Areas you will have to think about
- Your data structures for convenient storage and retrieval (particularly connected to: voting & sorting, comments and tags)
- Choosing a cool 'usp'/model/use case for the site (particularly connected to: 'who can edit' / comments and answers / tags)
- Having good content (particularly connected to: 'who can edit' / voting and sorting / moderators)
- CSS (It's really hard! And frustrating) (Particularly connected to: Looking sexy! :kiss:)
