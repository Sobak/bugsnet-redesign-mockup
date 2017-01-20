# bugs.php.net redesign mockup

It all started as an experiment. Due to my absolute lack of design skills I wanted
to check whether PHP.net homepage's design would suit needs of our bugtracker.

The Thing you are watching is mostly result of shameless copy&paste with a few CSS
overrides. I'd like, however, to call it *interface unification*. That sounds
better.

Any contributions or opinions are most certainly welcome. Just please remember,
it's my highly subjective idea, not an official PHP.net proposal.

Of course, I would like to implement it in the future if the feedback will be
positive.

## Demo
Online demo lives [here](http://sobak.pl/php-bugs-mockup). Please mind I update
it manually so from time to time it might get out of sync with this repository.

## Screenshots
Those can be a bit outdated but give general look&feel of this redesign.

![Homepage](http://sobak.pl/img/screenshots/RlgdlJXy.png)

![Reporting bug](http://sobak.pl/img/screenshots/h0KlB23G.png)

![Single bug](http://sobak.pl/img/screenshots/FMquEAcZ.png)

![Search bugs](http://sobak.pl/img/screenshots/0jUOng5Q.png)

## Functional changes
While this project focuses mainly on design changes, it aims for a few subtle changes in how
the bugtracker works as well. This section notes them so that everything should be clear when
the official discussion on php.net mailing list will happen.

### Simplifying bug votes
My idea is to change them to be simple yes/no vote. It drastically improves UX. We need to
decide upon migration path for current votes, though. There are two types of them, as far as
I can see and importance has its weight what wouldn't be a case with proposed simpler approach.

### Simplifying bug content itself
Currently values of *Description*, *Test script*, *Expected result* and *Actual result* form
fields are all concatenated into one database field. I'd like to strip the first part:
```
Description
-----------
```

but I propose to do this on read so no data migration will be required.

### Hide "Developer" tab for unauthenticated users
Not so important and adds one more click so I won't fight for it too much. Just a suggestion.
It would simplify interface and the code as well, though.

### Client-side search/autocompletion for "Package affected" field
It's rather self-explanatory and non-controversial, I think.
