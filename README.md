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

![Reporting bug](http://sobak.pl/img/screenshots/L1LcRXOO.png)

![Single bug](http://sobak.pl/img/screenshots/hxiThOcP.png)

![Search bugs](http://sobak.pl/img/screenshots/0jUOng5Q.png)

## Functional changes
While this project focuses mainly on design changes, it aims for a few subtle changes in how
the bugtracker works as well. This section notes them for the purpose of eventual php.net
mailing list discussion.

### Simplifying bug votes
My idea is to change them to be simple yes/no vote. It drastically improves UX. We need to
decide upon migration path for current votes, though. There are two types of them, as far as
I can see and importance has its weight what wouldn't be a case with proposed simpler approach.

### Show attatched patches and pull requests as comments
Since we have filters available for the bug comments' section finding them shouldn't be an issue.
My proposal is to change categories from "Git/SVN Commits" to "Commits/Patches" and "Related reports"
to "Related", including related pull requests.

When it comes to the migration: it seems that database table for patches contains all required data
so it should be achieveable with simple `UNION` with comments table. Pull requests are lacking time
they were added in, so my proposal is to add the field, set its value to current date for existing
attatchments and of course set it on new records creation. It shouldn't cause many troubles, IMO.

### Stats page simplification
Firstly, I suggest to drop [lstats.php](https://bugs.php.net/lstats.php) if it's really as
unused and forgotten as it seems to be.

Secondly, I'd also like to remove *PHP Versions for recent bug reports* section from the
[stats.php](http://bugs.php.net) page. In its current shape it's way less useful than
using "Version" field in advanced search which returns more accurate results and has more
flexibility. If it's, however, used by anyone, I have no problem with letting it live.

### Remembering last selected comment filter is removed
Currently bugs.php.net remembers last selected type of bug comments to filter, using cookies. This
feature is missing in this project but if anyone thinks it's useful it can be reimplemented.

### Simplifying bug content itself
Currently values of *Description*, *Test script*, *Expected result* and *Actual result* form
fields are all concatenated into single database field. I'd like to strip the first part:
```
Description
-----------
```

but I propose to do this on read so no data migration will be required and the change would
be fully reversible.

### Hide "Developer" tab for unauthenticated users
I won't insist on that too much as it adds a few clicks for the workflow from time to time.
Just a suggestion for a simpler interface and related code.

### Client-side search/autocompletion for "Package affected" field
It's rather self-explanatory and non-controversial, I think.
