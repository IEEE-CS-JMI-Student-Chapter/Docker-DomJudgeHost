# Docker Files for Domjudge Judgehost

```
$ docker-compose -f docker-compose-judgehost.yml up --build
```



### Environment Variables 

The following environment variables are supported by the judgehost container:

CONTAINER_TIMEZONE (defaults to Europe/Amsterdam): allows you to change the timezone used inside the container.
DOMSERVER_BASEURL (defaults to http://domserver/): base URL where the domserver can be found. The judgehost uses this to connect to the API. Do not add api yourself, as the container will do this!
JUDGEDAEMON_USERNAME (defaults to judgehost): username used to connect to the API.
JUDGEDAEMON_PASSWORD (defaults to password): password used to connect to the API. This should be the password displayed for the judgehost user when the domserver container was started. Like with the mysql passwords, you can also set JUDGEDAEMON_PASSWORD_FILE to a path containing the password instead.
DAEMON_ID (defaults to 0): ID of the daemon to use for this judgedaemon. If you start multiple judgehosts on one (physical) machine, make sure each one has a different DAEMON_ID.
DOMJUDGE_CREATE_WRITABLE_TEMP_DIR (defaults top 0): if set to 1, a writable temporary directory will be created for submissions. This only works for DOMjudge versions >= 6.1.
RUN_USER_UID_GID (defaults to 62860): UID/GID of the user that will submissions. Make sure this UID/GID is not used on your host OS.
