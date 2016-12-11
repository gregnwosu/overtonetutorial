# tutorial

a clojure library for exploring music theory

## Usage

jack-in
from the repl

``` clojure
(use 'overtone.live)
```

then go back to the code (C-z)
you can evaluate expressions in the repl (C-x C-e)
or (C-c)

note: the reply seems to traverse the tree looking for records to
evaluate so evaluating a ancestor expression may trigger descendent
expression evaluation and if they create sounds you may get some weird
random notes being played as the reply traverses the dependency graph.

## License

Copyright © 2016 FIXME

Distributed under the Eclipse Public License either version 1.0 or (at
your option) any later version.
