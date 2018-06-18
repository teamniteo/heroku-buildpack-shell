Heroku Buildpack: Shell
=====================

Run custom commands during the build process.


Description
-----------

This buildpack allows to execute arbitrary commands on the build dyno during the build process.

Just create the file `.heroku/run.sh` in the root directory of your application and write in this file the commands that you want to execute. This file is then ran in *subshell* by the `compile` script of this buildpack. That is, the commands in `.heroku/run.sh` are executed on the build dyno as they would be part of the `compile` script.

Available build-specific variables are `BUILD_DIR`, `CACHE_DIR`, and `ENV_DIR`.

The initial working directory is the root directory of your application(BUILD_DIR).

Usage
-----

Simply do:

~~~bash
# Create file '.heroku/run.sh' containing bash commands
echo 'echo "hello world"' >.heroku/run.sh

heroku buildpacks:set https://github.com/niteoweb/heroku-buildpack-shell.git
~~~

License
-------
Based on https://github.com/weibeld/heroku-buildpack-run/

Licensed under the MIT License. See [LICENSE.md](LICENSE.md) file.

We're hiring!
-------------

At Niteo we regularly contribute back to the Open Source community. If you do too, we'd like to invite you to [join our team](https://niteo.co/careers)!
