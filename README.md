# teamspeak3-scripts
Simple scripts for updating and starting/stopping a Teamspek3 Server

## Warnings ##

This scripts assume 2 things:
 1. THIS IS NOT A TURNKEY SOLUTION. It's just what I use, and might help you too.
 2. there exists a "ts3" user for running the server(s)
 3. every folder in /srv/teamspeak3/ is a Teamspeak server.
 4. You have a working backup. Updating your Server blindly by script can end bad. (duh)

## How To Use ##

Create your TS3 Servers in /srv/teamspeak3/[servername]/ since the update script doesn't check for a existing installation you probably can just create a folder and run the updater.

Start your server with
```
systemctl start teamspeak3@[servername].service
```
For autostart on boot up change "start" to "enable".

Add a line to your root's Crontab similar to this:
```
# m h  dom mon dow   command
  5 8   *   *   *    /usr/local/bin/updateTS
```
This will update all the servers at 5:08 AM if a new version is available.

I'm happy for pull requests which might actually make this a turnkey solution. But if you only run 1 Server this is kind of a "set up and forget" kinda thing.
