## Week 6: 2022-01-10 to 2022-01-14

At the start of this week, it was expected to switch gears from the `make` deriver to `eq`+`compare`. However, it was discovered there are more features to add to `make`! Below is a short summary of the development.

### Mentors' call

As usual, the weekly call with mentors served to guide and support the progress in a right direction. The call covered the following:
- Finalizing `make`
    - Opening the PR: it's time to do it! Most of what will be done from now on will be details, and can be done in parallel with working on other derivers. The remaining tasks can even be detailed in opened issues and left for later if not a priority.
    - Changes to `make`...
        - Document the deriver in the readme
        - Add a changelog
        - Add a license (Sonja tasked with figuring this out)
        - Correct uses of `raise_errorf`
    - **Very important notice from Sonja**: Through [this Discuss thread](https://discuss.ocaml.org/t/syntax-proposal-optional-record-fields/9070), Sonja found a `ppxlib`-based implementation of `make`, [found here](https://github.com/bn-d/ppx_make).
        - It supports `option` fields and a `[@default]` annotation, and is well-written, documented.
        - Original `ppx_deriving` worked on `option` fields, so _this needs to be implemented_.
        - Might be useful to find all `opam` packages that use `ppxlib` (reverse dependencies), in order not to miss another very relevant project!
- Starting with `eq`, `ord`/`compare`
    - **This week's goal**: understand how the JaneStreet implementation works. 
        - In order to do that, make a new branch that has a functioning `eq` deriver, extracted from the `eq`+`compare` bundle. 
        - Keep thinking about what code is common to both `eq` and `compare`, what should be in a module, what is common with `make`, any observations that might help with deciding on the architecture of `standard_derivers` in general and its implementation of `eq` and `ord` in particular. 
- OCaml community efforts 
    - Working with other people
        - Paul Elliot might be available to pair on correcting the way errors are done
        - Might be possible to also find someone other then Sonja and Shon to help with architecture decisions
        - The author of `ppx_make` might be interested as well (Sonja will connect with them)
        - Sonja is starting an open invitation biweekly meetings on the `ppx` ecosystem 
    - Writing a blog post ...
        - On what's been done so far 
        - Toward a general-audience to explain the project 
        - To expand on first post
        - To mark the halfway point of the internship

### Pairing 

Find the notes for the [Monday session with Shon](../pair-programming/2022-01-10.md) and the Wednesday session with Sonja.

### Missing features of `make`

Learning about `ppx_make` revealed how the work so far might have focused more on the JaneStreet implementation than the original one in `ppx_deriving`. A needed return to the [`ppx_deriving` readme](https://github.com/ocaml-ppx/ppx_deriving/#plugin-make) showed there were more missing features, namely: 
- A `[@main]` annotation that makes the specified field the last to be accepted in the derived constructor function
- Optional arguments, which allows for fields to have a default value. This can be done in the following ways:
    - fields of types `'a option`
    - fields of types `'a list`
    - fields with a `[@default]` annotation
- A `[@split]` annotation, which (quoting the readme) "corresponds to two arguments: mandatory argument `x` and optional argument `xs` with types `'a` and `'a list` correspondingly"
