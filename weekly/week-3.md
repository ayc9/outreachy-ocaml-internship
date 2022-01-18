## Week 3: 2021-12-20 to 2021-12-23

With the bulk code of the `make` deriver ready [in this fork](https://github.com/ayc9/ppx_fields_conv/tree/create) of `ppx_fields_conv`, there remained the following steps to complete the work on this first deriver:
1. Add a test for the structure in `deriving_inline.ml`
2. Replace the name `create` with `make`, and change derived function's name to include the original type's name, i.e. `make_t` for a record type `t`.
    - [This is done here](https://github.com/ocaml-ppx/ppx_deriving/blob/6198c82aa38b023b4402f4085cbfda195571d8ed/src_plugins/make/ppx_deriving_make.cppo.ml#L135) in the old implementation of `make` in `ppx_deriving`
3. Move code from the fork of `ppx_fields_conv` to a fork of `standard_derivers`. 
4. Remove the dependency on `base`. This was done in week 4.

Find details on steps 2. and 3. in the sections below.

### Renaming the derived function `make_t`

### Building a repo from scratch

Week 3 saw functioning code for a `create` deriver move from [this fork](https://github.com/ayc9/ppx_fields_conv/tree/create) of `ppx_fields_conv` into this branch of `standard_derivers`, a previously empty placeholder repo.
