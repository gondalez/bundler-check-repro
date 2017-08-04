# Background

This repo reproduces the state where the version in the `Gemfile` was updated but the
developer forgot to run bundle update.

Running `bundle check` by itself updates the lockfile. But what I really want is a way to
detect the error quickly during CI so the developer knows to `bundle update` and commit
the lockfile change.

# Repro

```
➜  bundler-check-repro (master) ✔ bundle check --dry-run
Resolving dependencies...
The Gemfile's dependencies are satisfied
➜  bundler-check-repro (master) ✔ bundle install --deployment
You are trying to install in deployment mode after changing
your Gemfile. Run `bundle install` elsewhere and add the
updated Gemfile.lock to version control.

the dependencies in your gemfile changed


You have added to the Gemfile:
* activesupport (~> 4.2.0)

You have deleted from the Gemfile:

* activesupport (~> 4.1.0)
```

# The command I wish I had :)

``` shell
➜  bundler-check-repro (master) ✔ bundle check --strict

Gemfile.lock has not been updated after changing your Gemfile.
Run `bundle install` elsewhere and add the updated
Gemfile.lock to version control.

the dependencies in your gemfile changed


You have added to the Gemfile:
* activesupport (~> 4.2.0)

You have deleted from the Gemfile:

* activesupport (~> 4.1.0)
```
