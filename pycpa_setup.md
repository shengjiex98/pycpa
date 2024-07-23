# Setup Tips for pyCPA

## Error when installing pygraphviz

`graphviz` is required for `pygraphviz`. See the [instructions](https://pygraphviz.github.io/documentation/stable/install.html).

### Linux
On Linux, `graphviz-dev` or `graphviz-devel` (depending on distribution) might be additionally required and should be installed through package manager.

### Mac OS
For Mac OS, the following is recommended
```
$ brew install graphviz
$ pip install pygraphviz
```

`graphviz` may be installed in a location that is not on the default search path. In this case, it may be necessary to manually specify the path to the `graphviz` include and/or library directories, e.g.
```
$ pip install --config-settings="--global-option=build_ext" \
              --config-settings="--global-option=-I$(brew --prefix graphviz)/include/" \
              --config-settings="--global-option=-L$(brew --prefix graphviz)/lib/" \
              pygraphviz
```
