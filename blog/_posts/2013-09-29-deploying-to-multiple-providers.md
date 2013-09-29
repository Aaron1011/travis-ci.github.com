---`
title: Deploying to Multiple Providers
created_at: Sun 29 Sep 2013 6:25:00 EST
author: Aaron Hill
layout: post
permalink: blog/2013-09-29-deploying-to-multiple-providers
---

At Travis CI, we've been hard at work adding support for deploying to your favorite cloud providers.
But, until now, you've been limited to choosing only one provider per repository.
Today, we're happy to announce support for deploying to multiple providers!
To set this up, simply as many `provider` sections as you want to your `.travis.yml`, placing a dash (-) before each `provider`.
For example, if you want to deploy to Heroku and Nodejitsu, set up your `.travis.yml` to look like this:

    deploy:
      - provider: heroku
        api_key: "YOUR HEROKU API KEY"
      - provider: nodejitsu
        user: "YOUR NODEJITSU USERNAME"
        password: "YOUR NODEJITSU API KEY"

If you have `before_deploy` and `after_deploy` sections set up, they will run before and after deploying to each provider you specify.
