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

## Contributing

### Upgrading the vendored Alloy version

From a trusted computer and network:

- Navigate to https://github.com/grafana/alloy/releases/latest
- Replace the contents of VERSION with the release tag like `vX.Y.Z`.
- Replace the contents of SHA256SUMS with the released [file](https://github.com/grafana/alloy/releases/download/latest/SHA256SUMS).

### Developing

Install [pre-commit](https://pre-commit.com/)

```console
pre-commit install
```

Test a compilation works with:

```console
bin/compile <your-app-dir> /tmp/cache /tmp
```

This repo can be used as an app to test the `example.alloy` config after setup
to push to the Heroku git URL.

```config
git push heroku main
```
