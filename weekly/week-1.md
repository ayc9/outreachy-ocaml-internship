## Week 1: 2021-12-06 to 2021-12-10

The first week mostly involved assessing the scope of work for the internship as well as getting familiar with the PPX ecosystem and its many repositories.

### Scope of the internship
The work will involved improving the PPX ecosystem by consolidating standard derivers to a single location in the `ocaml-ppx` project, and to an implementation standard based on the `Deriving` module of `ppxlib`. See below table for more details.

### List of repos relevant to PPX derivers
| Link to repo  | What is it?  | How will it be used in this project?  |
| ------------ | ------------ | ------------ |
| [ocaml-ppx/ppx_deriving](https://github.com/ocaml-ppx/ppx_deriving "ocaml-ppx/ppx_deriving") | All standard derivers as plugins, before `ppxlib` became what it is now | Any deriver that has not yet been reimplemented using ppxlib will need to be reimplemented in the new `standard_derivers` repo |
| [ocaml-ppx/ppxlib](https://github.com/ocaml-ppx/ppxlib "ocaml-ppx/ppxlib") | Most updated and comprehensive library for everything to do with PPX  | This library will give all the tools to use for all reimplementations of derivers |
| [ocaml-ppx/standard_derivers](https://github.com/ocaml-ppx/standard_derivers "ocaml-ppx/standard_derivers") | Newly created repo for standard PPX derivers that are yet to be consolidated, collected, or written | This repo will hold any Issues that are to be created during the project, and will contains any reimplemented derivers that are worked on. |
| [thierry-martinez/ppx_show](https://github.com/thierry-martinez/ppx_show "thierry-martinez/ppx_show") | The show deriver based on `ppxlib`| This implementation will be upstreamed to the new `standard_derivers` repo |
| [janestreet/ppx_compare](https://github.com/janestreet/ppx_compare "janestreet/ppx_compare") | Deriver equivalent to `eq` and `ord`, with dependency on `base` | This implementation will be updated to no longer depend on `base` and to follow the larger ecosystem's syntax conventions, also to the new `standard_derivers` repo |
| [janestreet/ppx_fields_conv](https://github.com/janestreet/ppx_fields_conv "janestreet/ppx_fields_conv") | Deriver equivalent to `make`, `iter`, `map` and `fold` with dependency on `base` | Same as above |

### Rough timeline
- Week 1: Read documentation,  understand project, learn how derivers are constructed through `show` deriver.
- Weeks 2 and 3:  Have a deriver rewritten to new repo and functioning.
    - Friday 12-24: off.
- Week 4:  Test writing and clean-up.
    - Friday 12-31: off.
    - Done with first deriver by end of December.
- Weeks 5, 6 and 7: Reimplement a second deriver.
    - Draft and share a blog post summarizing work up to this halfway point.
- Weeks 8, 9 and 10: Reimplement a third deriver.
- Weeks 11, 12 and 13: Implement fourth deriver if there is time, document project, buffer time.
    - Draft and share a blog post summarizing work of whole internship.

### Communication with mentors
 In order to ensure regular communication,  the mentors have encouraged the following
- Daily written check-ins on Slack, at 10am EST
- Weekly written reports due Mondays, at 10am EST
- Weekly calls on Tuesdays, at noon EST

### Further habits for a steady internship
The following are some other habits to maintain consistent and progressive efforts throughout the internship
- Regular reading of OCaml Discuss forum and Discord
- Compilation of a list of resources used throughout the internship, found in this file
- Some easy programming exercises in OCaml to pick up the language
- Fix work hours to intersect with CET

### Overview of week 1 efforts
- Held call with mentors to delimit scope of work. This document contains main points from that call
- Started this notes repo to document work
- Read Tarides blogpost on PPX. [See notes here](https://github.com/ayc9/outreachy-ocaml-internship/tree/main/technical-notes/tarides-blogpost.md)
- Studied `show` implementations. [See notes here](https://github.com/ayc9/outreachy-ocaml-internship/tree/main/technical-notes/deriver-show.md)
- Had pair programming call with Sonja. We went over an example implementation of a deriver. [See notes here](https://github.com/ayc9/outreachy-ocaml-internship/tree/main/pair-programming/2021-12-10.md)
