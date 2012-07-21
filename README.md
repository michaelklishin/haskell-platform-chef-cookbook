# Haskell Platform Chef Cookbook

This is an OpsCode Chef cookbook that provisions GHC 7.4 and Haskell Platform 2012.02
from source.

All executables are installed under `/usr/local/bin`. Cabal executables path under `~/.cabal/bin`
is prepended to PATH via a shell script installed under `/etc/profile.d/`.


## GHC and Haskell Platform Versions

This cookbook currently provides

 * GHC 7.4 with Platform 2012.02
 * GHC 7.0 with Platform 2011.02.

but no other combinations, in part due to Platform requirements on the GHC version used to
compile it.


## Supported OSes

Recent Debian or Ubuntu releases (10.04+) should work.


## Recipes

 * `haskell::source` provisions the most recent GHC (7.4) and Haskell Platform (2012.02) releases from source.
 * `haskell::package` provisions older GHC (7.0) and Haskell Platform (2011.02) releases from apt packages.

Main recipe includes `haskell::source`.


## Attributes

* `node[:ghc]:version`: GHC version. `"7.4.1"` by default. Keep in mind that Haskell Platform currently stringly checks GHC version to be equal to `7.4.1` and thus fails to build with GHC 7.4.2.


## Dependencies

None.


## Copyright & License

Michael S. Klishin, 2012.

Released under the [Apache 2.0 license](http://www.apache.org/licenses/LICENSE-2.0.html).
