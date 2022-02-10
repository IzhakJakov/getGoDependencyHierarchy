getGoDependencyHierarchy
========================
A utility for getting the dependencies of a specific package in a Go module.

Example using Zsh on MacOS
--------------------------
Looking for `github.com/spf13/cobra` with tag `v1.1.1` in `grokify/go-aha`.  
A module is directly using[^1] the module which is directly under it.
```sh
  $ git clone 'https://github.com/grokify/go-aha.git'
 
  $ cd go-aha
 
  $ git checkout v0.2.3

  $ getGoDependencyHierarchy 'github.com/spf13/cobra@v1.1.1'
            github.com/grokify/go-aha
                       ⬇
       github.com/grokify/gocharts@v1.16.8
                       ⬇
    github.com/wcharczuk/go-chart@v2.0.1+incompatible
                       ⬇
      github.com/blend/go-sdk@v1.20211204.3
                       ⬇
          github.com/spf13/cobra@v1.1.1
```
[^1]: Directly using means the module is directly inside `go.mod` not just `go.sum`.
