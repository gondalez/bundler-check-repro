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
