[![Build Status](https://travis-ci.com/thvnx/mlmpfr.svg?branch=release_316)](https://travis-ci.com/thvnx/mlmpfr)

# mlmpfr
OCaml bindings for MPFR.

#### build and install

*mlmpfr* depends on _ocamlfind_, _oasis_, _ocaml_ version >= 4.04, and
_MPFR_ library version >= 3.1.6.

From source: in mlmpfr main directory.

```bash
oasis setup
./configure --enable-tests
make
make test
make install
# `make uninstall` to remove mlmpfr library.
```

From _opam_.

```bash
opam install mlmpfr
# `opam remove mlmpfr` to remove the package.
```

#### documentation

Run:
```bash
make doc # Generate HTML documentation
```
or see [here](https://thvnx.github.io/mlmpfr/).

#### usage

For example, let _example.ml_ as follows:

```ocaml
module M = Mpfr

let _ =
  let op = M.make_from_float (~-. 1. /. 3.) in
  Printf.printf "%s\n" (M.get_formatted_str (M.cos op))
```

Compile the above code with:

```bash
ocamlfind ocamlopt -o a.out -linkpkg -package mlmpfr example.ml -cclib -lmpfr
```
