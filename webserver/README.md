Some scripts to run this Jila back end software on your server, using Docker.
The docker-compose file is mostly just dev stuff, atm.

### Things to work on:
For some reason this isn't installing a particular rake version that's needed (10.3.2),
so I'm gonna have to fix that. At this point, if you run these dockerfiles as they
are, expect to have to go in and run `bundle install --deployment` before actually
being able to run this thing locally (using docker).


<3 <3  
