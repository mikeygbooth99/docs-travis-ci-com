---
title: anynines Deployment
layout: en
deploy: v2

---

You now have the amazing ability to deploy directly to [anynines](http://www.anynines.com/) after a successful build on Travis CI

## The Easy Way

Go Grab the Travis gem from [GitHub](https://github.com/travis-ci/travis.rb) and run this command:

`travis setup anynines`

You will be asked to answer a few simple questions about your anynines setup and Travis will take care of the rest!

## The Slightly Harder Way

So you want to write your own `.travis.yml`, fine.  Here is the minimum required to get up and running

```yaml
 deploy:
   provider: anynines
   username: johndoe@example.com
   password: secretpassword
   organization: myorganization
   space: staging
   app_name: My app name                # (optional)
```
{: data-file=".travis.yml"}

***Make sure that you encrypt your password before pushing your updated .travis.yml to GitHub.***

This can be easily accomplished using the Travis gem above and running:

```
travis encrypt --add deploy.password
```

### Conditional releases

You can deploy only when certain conditions are met.
See [Conditional Releases with `on:`](/user/deployment#conditional-releases-with-on).
