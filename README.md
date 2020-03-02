# rubyci-recipe

## Usage

### Prepare environment for hocho apply

1. Added ssh configuration to `~/.ssh/config`.
2. Install curl and rsync in target VM.
3. Added `NOPASSWD` option to `/etc/sudoers`.

### Run hocho

```bash
# dry-run
bundle exec hocho apply -n chkbuild004.hsbt.org

# apply
bundle exec hocho apply chkbuild004.hsbt.org
```

### All chkbuild

```bash
# dry-run
for i in 004 006 008 011 012; do bundle exec hocho apply -n "chkbuild${i}.hsbt.org"; done

# apply
for i in 004 006 008 011 012; do bundle exec hocho apply "chkbuild${i}.hsbt.org"; done
```

### OpenCSW [experimental]

```bash
# dry-run
bundle exec hocho apply --config=hocho-opencsw.yml -n login.opencsw.org

# apply
bundle exec hocho apply --config=hocho-opencsw.yml login.opencsw.org
```

## TODO for chkbuild user

* Added rbenv PATH to `.bash_profile`
* Invoke `gem i aws-sdk -v "~>2"` with rbenv ruby.
* Added crontab with aws credentials.

## License

[Ruby License](https://www.ruby-lang.org/en/about/license.txt)
