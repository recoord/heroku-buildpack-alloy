# Heroku buildpack: alloy

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks)
that allows one to run [Grafana Alloy](https://grafana.com/docs/alloy/latest/)
in a dyno alongside application code.  It is meant to be [used in conjunction
with other
buildpacks](https://devcenter.heroku.com/articles/using-multiple-buildpacks-for-an-app)
to monitor applications using the Prometheus ecosystem.

## Version

The Alloy GitHub release and version is located in the checksum file.

## Usage

In your Procfile, start alloy with a configuration then your application.

```console
bin/start-alloy --confg=path/to/config.alloy YOUR_PROC_CMD
```
