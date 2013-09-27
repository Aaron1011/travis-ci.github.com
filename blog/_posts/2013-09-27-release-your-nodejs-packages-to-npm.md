---
title: Release your NodeJS packages to NPM
created_at: Fri 27 Sep 2013 19:10:00 EST
author: Aaron Hill
layout: post
permalink: blog/2013-09-27-release-your-nodejs-packages-to-npm
---

At Travis CI, we've been adding support for deploying to many different cloud providers,
as well as package hosting sites like RubyGems and PyPI. We didn't want NodeJS users to feel left out, so today we're happy to announce support for releasing packages to NPM!

Setting this up is just like deploying or releasing to any other service. Just add the following lines to your `.travis.yml`:

    deploy:
       provider: npm
       email: "YOUR-EMAIL-ADDRESS"
       api_key: "YOUR-API-KEY"

To retrieve your api key, you'll need to have the `npm` tool installed. Run the following command:

    $ npm login

Follow the prompts to log in to your NPM account. You can then find your API key in your ~/.npmrc file.

That's it!

This feature is immediately available to all our users including our [Travis Pro](http://travis-ci.com) customers.

### Is your provider still missing?

If you'd like to see your provider supported on Travis CI, [contact us](mailto:support@travis-ci.org) or [fork us on Github](https://github.com/travis-ci/dpl).
