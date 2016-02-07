# heroku-buildpack-swig

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) that
allows you to install swig which is a system dependency needed for many libraries to function correctly. E.g. M2Crypto.

Use this in conjunction with the [Heroku buildpack: multi](https://github.com/heroku/heroku-buildpack-multi) to use your buildpack of choice once swig is installed. E.g. [Heroku Python buildback](https://github.com/heroku/heroku-buildpack-python).

## Usage

To use this buildpack you'll first need to set the multi buildpack as your custom buildpack:

    $ heroku buildpacks:set https://github.com/heroku/heroku-buildpack-multi.git

From here you will need to create a `.buildpacks` file which contains this buildpack and then the other buildpacks which will trigger dependencies on swig.

    $ cat .buildpacks
    https://github.com/jamarparris/heroku-buildpack-swig
    https://github.com/heroku/heroku-buildpack-python

## License

MIT
