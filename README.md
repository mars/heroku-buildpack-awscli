Heroku buildpack: AWS CLI
=========================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) that
allows one to run [AWS CLI](https://aws.amazon.com/cli/) in a dyno alongside application code.

Usage
-----

Usually this buildpack will supplement the main buildpack for an app.

This example prepends this buildpack as `--index=1` to any existing buildpacks for the app:

```bash
heroku buildpacks:add --index=1 mars/awscli
heroku config:set \
  AWS_ACCESS_KEY_ID=<aws-access-key> \
  AWS_SECRET_ACCESS_KEY=<aws-secret-access-key> \
  AWS_DEFAULT_REGION=<default-aws-region>
git push heroku master
```
