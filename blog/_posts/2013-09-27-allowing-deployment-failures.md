---
title: Allowing Deployment Failures
author: Aaron Hill
created_at: Fri 27 Sep 2013 15:15:00 EST
layout: post
permalink: blog/2013-09-27-allowing-deployment-failures
---

If you've been using continuous deployment on Travis CI, you may have noticed that if anything goes wrong during the deployment process,
it causes that job to be marked as failed or errored. We've had mixed reactions to this: it's considered a bug by some, and a feature by others.

Today, we're happy to announce that you can now decide whether or not a deployment problem should cause a job to fail.
Simple add `allow_failure: true` to the `deploy` section of your `.travis.yml`. It should look like this:

    deploy:
      provider: ...
      allow_failure: true

Now, any problem during deployment won't reflect in the status of a job.
