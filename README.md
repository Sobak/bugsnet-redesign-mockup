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
Those can be a bit outdated but give general look of this redesign.

![Homepage](http://sobak.pl/img/screenshots/RlgdlJXy.png)

![Reporting bug](http://sobak.pl/img/screenshots/h0KlB23G.png)

![Single bug](http://sobak.pl/img/screenshots/FumRB4Zp.png)

![Search bugs](http://sobak.pl/img/screenshots/UbmDoDzb.png)

## Functional changes
While this project focuses mainly on design changes, it aims for a few subtle changes in how
the bugtracker works as well. This section notes them so that everything should be clear when
the official discussion on php.net mailing list will happen.

- simplifying bug votes: I suggest changing it to simple yes/no vote for both simpler design and
  user experience; dealing with existing votes and their weights remains open question
- hiding "Developer" tab for non-logged in users and "Add comment" for logged in - just for the
  sake of readability
- stripping *"Description\n--------"* from the bug content on reading from the database -  no data
  migration will be required
- I'd love to switch for something like ReCaptcha but it's out of scope here perhaps
- adding client-side search for the *Package affected* select - it seems to be non-controversial
  though
