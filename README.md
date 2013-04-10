This project is no longer maintained :-( HTML grep/sed magic last seen working: 2013-04-10. 

PLAYCOM-WATCHER
===============

Monitor prices on [Play.com](http://www.play.com).

Emails a notification if a given product's price drops below a set limit. 

## Instructions

1. Setup mail. 
2. Put your URLs and price limits of interesting products to `playcom.list`.
3. Change the value of `YOUR_EMAIL` variable in `playcom-watcher` to your email address.
4. Run `playcom-watcher`.

## Running playcom-watcher regularly

Use cron or launchd.

### Linux / cron

1. `crontab -e`.
2. Add line: `@hourly ~/bin/playcom-funtimes/playcom-watcher`.
3. Now `playcom-watcher` runs hourly.

### Mac OS X / launchd

1. Copy `fi.viiksipojat.playcom-watcher.plist` into `~/Library/LaunchAgents/`.
2. Modify `ProgramArguments` path in plist to point where you installed `playcom-watcher`. Note that you can't use `~`.
3. Add to launchd: `launchctl load ~/Library/LaunchAgents/fi.viiksipojat.playcom-watcher.plist` (or reboot).
4. Now `playcom-watcher` runs hourly. Start manually anytime: `launchctl start fi.viiksipojat.playcom-watcher`.

## Inspiration

This project borrows heavily from [muumi-dl](https://github.com/sampula/muumi-dl) by the ever so great SAMPUMON!