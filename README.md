# hasdoc locates locally built Haskell library docs

You specify package names or module names, and this program lists or xdg-open's
(default) the local html files.

Example: By package names:

```
$ hasdoc -l base cassava random-1.2.1
/usr/local/.ghcup/ghc/8.10.7/share/doc/ghc-8.10.7/html/libraries/base-4.14.3.0/index.html
/home/trebla/.cabal/store/ghc-8.10.7/cassava-0.5.2.0-7348abe88993efbfaa6c704ca0236811f232f3553e644a9baa5d0ab588bc6f60/share/doc/html/index.html
/home/trebla/.cabal/store/ghc-8.10.7/random-1.2.1-e2a470bddae1da56736c04a4f90f71d380a26095b22e0ef3e73f4aa440aab864/share/doc/html/index.html
```

Example: By module names:

```
$ hasdoc -l -m System.IO Data.Csv System.Random.Stateful
/usr/local/.ghcup/ghc/8.10.7/share/doc/ghc-8.10.7/html/libraries/base-4.14.3.0/System-IO.html
/home/trebla/.cabal/store/ghc-8.10.7/cassava-0.5.2.0-7348abe88993efbfaa6c704ca0236811f232f3553e644a9baa5d0ab588bc6f60/share/doc/html/Data-Csv.html
/home/trebla/.cabal/store/ghc-8.10.7/random-1.2.1-e2a470bddae1da56736c04a4f90f71d380a26095b22e0ef3e73f4aa440aab864/share/doc/html/System-Random-Stateful.html
```

The -l requests listing the pathnames. If I omit -l, this program by default
runs xdg-open for each pathname, so they are open in your web browser.

Options:

```
  -h          This help message.
  -g VERSION  Manually specify GHC version.
              It is OK to specify a partial version number, e.g., 8.8,
              provided that "ghc-8.8 --numeric-version" works. If it reports
              8.8.4 for example, then 8.8.4 is used.
  -p          NAMEs are package names (default).
  -m          NAMEs are module names.
  -w          ("view") xdg-open documentation files in web browser (default).
  -l          ("list") Print documentation filenames to stdout.
```
