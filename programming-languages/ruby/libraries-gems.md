# Libraries \(Gems\)

## Install a Library

[Doc](https://guides.rubygems.org/command-reference/#gem-install)

```text
gem install GEMNAME [GEMNAME ...] [options] -- --build-flags [options]
```

### User install

Option: `--user-install`

Needs to add `~/.gem/ruby/$RUBY_VERSION/bin` to `PATH` variable.

## List Installed Libraries

```ruby
gem list
```

## Import a Library

Require a gem

```ruby
require 'rake'
```



