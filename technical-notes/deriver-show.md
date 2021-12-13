_Below are notes on the following two implementations of the `show` deriver: the first as found in `ppx_deriving` and the second as reimplemented under `ppx_show`. Links to the repos are at the bottom of this page._

### What to look for in an implementation using `ppxlib`
- In `my_ppx_deriver.ml` we find:
``` 
open Ppxlib

let str_type_decl_generator =
  Deriving.Generator.make_no_arg
    ~attributes
    expand_str

let sig_type_decl_generator =
  Deriving.Generator.make_no_arg
    ~attributes
    expand_sig

let my_deriver =
  Deriving.add
    ~str_type_decl:str_type_decl_generator
    ~sig_type_decl:sig_type_decl_generator
    "my_deriver"
```
- To compile, we find
```
(library
 (public_name my_ppx)
 (kind ppx_deriver)
 (libraries ppxlib))
 ```

- A `Deriving.add` function declared as:
```
val add
  :  ?str_type_decl:(structure, rec_flag * type_declaration list) Generator.t
  -> ?str_type_ext :(structure, type_extension                  ) Generator.t
  -> ?str_exception:(structure, extension_constructor           ) Generator.t
  -> ?sig_type_decl:(signature, rec_flag * type_declaration list) Generator.t
  -> ?sig_type_ext :(signature, type_extension                  ) Generator.t
  -> ?sig_exception:(signature, extension_constructor           ) Generator.t
  -> ?extension:(loc:Location.t -> path:string -> core_type -> expression)
  -> string
  -> t
  ```
Here, `"my_deriver"` is mandatory and defines how users are going to invoke the deriver, i.e. `[@@deriving my_deriver]`

Read the notes further with example in front of you.

### As found in `ppx_show`

### As found in `ppx_deriving`

### Links
- [Tarides blog outlining how to write a deriver rewriter](https://tarides.com/blog/2019-05-09-an-introduction-to-ocaml-ppx-ecosystem#writing-a-deriver)
- [`show` deriver implementation using `ppxlib`](https://github.com/thierry-martinez/ppx_show/)
- [`show` deriver implementation without `ppxlib`](https://github.com/ocaml-ppx/ppx_deriving/blob/master/src_plugins/show/ppx_deriving_show.cppo.ml)
