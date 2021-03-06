[![Version     ](https://img.shields.io/gem/v/gem_updater.svg?style=flat)](https://rubygems.org/gems/gem_updater)
[![Build Status](https://img.shields.io/travis/MaximeD/gem_updater/master.svg?style=flat)](https://travis-ci.org/MaximeD/gem_updater)
[![Code Climate](https://img.shields.io/codeclimate/github/MaximeD/gem_updater.svg?style=flat)](https://codeclimate.com/github/MaximeD/gem_updater)
[![Inline docs ](http://inch-ci.org/github/MaximeD/gem_updater.svg?style=flat)](http://inch-ci.org/github/MaximeD/gem_updater)

# GemUpdater: update your gemfile and retrieve changelogs

Every week or so, you wish to update your `Gemfile`,
to do so, you just have to launch `bundle update`.

Problem is updates *may* break things.
And obviously you need to know what may have broke before pushing your code to production.
Before running your test suite and checking everything is fine,
the first thing you do is probably to look for the changelogs of updated gems.

This process can be quite time consumming:
you need to check on the internet for every updated gems, find where their changelog is hosted,
and probably link to it in your commit message so that other developers will have a chance
to review it too.

`gem_update` will do exactly that for you.
It updates your `Gemfile` (via `bundle update`) and finds links for changelogs of updated gems.
All you have to do is to copy paste the output to the commit message, and you're done!
Obviously, you still have to read changelogs and adapt your code though ;)

## Installation and usage

**You must have ruby 2.0 or above to use it!**

```
gem install gem_updater
gem_update
<copy paste of output to commit message>
```

### Diff format

By default, diff for your gems will look like the following:

```
* gem_1 0.1 → 0.2
[changelog](https://github.com/maintainer/gem_1/CHANGELOG.md#02)

* gem_2 3.4.2 → 3.4.3
[changelog](https://github.com/maintainer/gem_1/CHANGELOG.md#343)
```

You can change it if you like by writing you own template `.gem_updater_template.erb` in your home directory.
[Look at default template](https://github.com/MaximeD/gem_updater/lib/gem_updater_template.erb) for an example on how to do it.

## Contributing

PRs are always welcome!
If you wish to contribute, do not hesitate to submit an issue or to open a pull request.
