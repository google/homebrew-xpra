This is not an official Google product.

# Homebrew formula for Xpra that works

Formula is written from scratch to make it harder, better, faster, stronger.

## Usage

1. Add this repo as a tap `brew tap timothybasanov/xpra`
2. Install Xpra: `brew install xpra` (use can use `--devel` for 0.15.x branch)
3. Use Xpra as you usually do: `xpra attach ssh:ubuntu.local:100`

## Development process

1. Clone this repo into `/usr/local/Library/Tap/timothybasanov/`
2. Add as an IntelliJ project
3. Edit `xpra.rb`
4. Reinstall xpra: `brew uninstall xpra ; brew install --verbose --debug --HEAD xpra`
5. I run live xpra server on a separate Ubuntu machine, here is how to debug xpra client:
    * python to use `/usr/local/bin/python` (to pick up GTK+ libs)
    * current directory `/usr/local/Cellar/xpra/HEAD`
    * file to run `libexec/bin/xpra`
    * source/compiled code should be on `PYTHONPATH`:
        1. `libexec/bin`
        2. `lib/python2.7/site-packages`
        3. `libexec/vendor/lib/python2.7/site-packages`
    * parameters `--debug=all --encoding=rgb attach ssh:ubuntu.local:100`
