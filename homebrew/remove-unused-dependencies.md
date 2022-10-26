# Remove unused dependencies

Calling `brew uninstall something` doesn't remove dependencies of `something`,
so we may end up with tons of unused stuff.

Fortunately, Homebrew added command called `autoremove`, which removes all such
dangling dependencies. Something like this:

```shell
brew uninstall imagemagick; brew autoremove
```
