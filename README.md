# How to Use Rubinius and Puma on Heroku

## In Three Steps

1. Install the Puma gem in your `Gemfile`

    `gem "puma", "~> 2.0.0.b6"`

2. Tell Heroku to use Puma as your webserver in your `Procfile` (at the root of your app)

    `web: bundle exec puma -p $PORT`

3. Specify Rubinius as your ruby engine in your `Gemfile`

    `ruby "1.9.3", :engine => "rbx", :engine_version => "2.0.0dev"`


## Confirmation

When you commit and push these changes to Heroku, if all goes well, you should see something this output:

    -----> Using Ruby version: ruby-1.9.3-rbx-2.0.0dev
    -----> Installing dependencies using Bundler version 1.3.0.pre.5
           Ruby version change detected. Clearing bundler cache.
           Old: ruby 1.9.2p290 (2011-07-09 revision 32553) [x86_64-linux]
           New: rubinius 2.0.0dev (1.9.3 release yyyy-mm-dd JI) [x86_64-unknown-linux-gnu]

To confirm that your app is really running on Rubinius 2.0, you can use the `console`.

    heroku run console

First ask what the `RUBY_ENGINE` is

    RUBY_ENGINE

You should get back `rbx`

    "rbx"

Next, ask what version of Rubinius is running

    Rubinius.version

It should be something that starts with `rubinius 2.0.0dev`

    "rubinius 2.0.0dev (1.9.3 release yyyy-mm-dd JI) [x86_64-unknown-linux-gnu]"

That's it! You're running Rubinius 2.0 on Heroku!
