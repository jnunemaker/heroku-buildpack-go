# Go Buildpack for Heroku

Sets up a Heroku dyno ready to run a [golang](http://golang.org) application.

## Setup

Create a `script/bootstrap` file that installs the application's dependencies.
Using [gopack](https://github.com/d2fn/gopack) is a popular option.

Create a `script/build` file that builds the application's binaries and places
them in `bin/`.

Create a `Procfile` that runs the binary:

```
web: bin/myapp -p $PORT
```

Configure Heroku to use the buildpack:

```
heroku config:set BUILDPACK_URL=git://github.com/alindeman/heroku-buildpack-go.git
```

Ship it! :shipit:

```
git push heroku master
```
