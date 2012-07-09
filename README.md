# heroku-config (with multi env support)

Provides a way for you to push/pull your Heroku environment to use locally.

## Installation

Add the heroku gem plugin:

    $ heroku plugins:install git://github.com/blakefrost/heroku-config.git
    heroku-config installed

Add the following to `.gitignore`:

    .env

## Usage

    # by default, existing keys will not be overwritten
    $ heroku config:pull
    Config for example written to .env.d/example

    # optional --overwrite allows you to have the pull overwrite keys
    $ heroku config:pull --overwrite
    Config in .env.d/example written to example

    # --interactive will prompt for each value to be overwritten
    $ heroku config:pull --overwrite --interactive
    BUNDLE_DISABLE_SHARED_GEMS: 1
    Overwite? (y/N)

    $ heroku config:push
    Config in .env.d/example written to example

## How it works

Your environment will be stored locally in a file named `.env`. This
file can be read by [foreman](http://github.com/blakefrost/foreman) to load
the local environment for your app.

Please remember to not commit your `.env` file to your repository.

## License

MIT License

## Author

David Dollar <ddollar@gmail.com>

## Contributors

Blake Taylor <blakefrost@gmail.com>
