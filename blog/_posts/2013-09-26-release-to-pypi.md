---
title: Release to PyPI from Travis CI
author: Aaron Hill
created_at: Thu 26 Sept 2013 20:25:00
layout: post
permalink: blog/2013-09-26-release-to-pypi.md
---

Recently, we added support for [deploying to RubyGems](/blog/2013-08-22-let-travis-push-your-rubygems).
Now, Python package developers can also enjoy continuous deployment, thanks to out new support for PyPI!

Just add the following lines to your `.travis.yml`:

    deploy:
      provider: pypi
      user: "YOUR_USER_NAME"
      password: "YOUR_PASSWORD" # should be encrypted with `travis encrypt`

To make things even simples, if you've installed [our command line tool](2013-08-22-let-travis-push-your-rubygems),
you can simply run the following command:

    $ travis setup pypi

Just follow the prompts to get set up releasing to PyPI.

If you've read about releasing to RubyGems from Travis CI, you may have heard about only releasing when a tagged commit is present.
It's just as easy to set up with PyPI.
Just add `on: tags: true` to your `deploy` section so that it looks like this:

    deploy:
      provider: pypi
      user: "YOUR_USER_NAME"
      password: "YOUR_PASSWORD"
      on:
        tags: true


### Is your provider still missing?

We've added support for lots of new providers, but if you'd like to see yours added, [let us know](mail:support@travis-ci.com),
or [send us a pull request](http://github.com/rkh/dpl).

Expect to see NPM support coming in the future!
