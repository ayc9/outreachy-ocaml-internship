## Week 1: 2021-12-06 to 2021-12-10

The first week mostly involved assessing the scope of work for the internship as well as getting familiar with the PPX ecosystem and its many repositories.

### Scope of the internship


### Rough timeline
- Weeks 1+2: Read documentation,  understand project, focus on `show` deriver.
- Week 3:  Have `show` deriver rewritten to new repo and functioning.
    - Friday 12-24: off.
- Week 4:  Test writing and clean-up.
    - Friday 12-31: off.
    - Done with `show` by end of December?
- Weeks 5, 6 and 7: Reimplement a second deriver.
    - Draft and share a blog post summarizing work up to this halfway point.
- Weeks 8, 9 and 10: Reimplement a third deriver.
- Weeks 11, 12 and 13: Implement fourth deriver if there is time, document project, buffer time.
    - Draft and share a blog post summarizing work of whole internship.

### List of repos relevant to PPX derivers
| Link to repo  | What is it?  | How will it be used in this project?  |
| ------------ | ------------ | ------------ |
| [ocaml-ppx/ppx_deriving](https://github.com/ocaml-ppx/ppx_deriving "ocaml-ppx/ppx_deriving") | All standard derivers as plugins, before `ppxlib` became what it is now | Any deriver that has not yet been reimplemented using ppxlib will need to be reimplemented in the new `standard_derivers` repo |
| [ocaml-ppx/ppxlib](https://github.com/ocaml-ppx/ppxlib "ocaml-ppx/ppxlib") | Most updated and comprehensive library for everything to do with PPX  | This library will give all the tools to use for all reimplementations of derivers |
| [ocaml-ppx/standard_derivers](https://github.com/ocaml-ppx/standard_derivers "ocaml-ppx/standard_derivers") | Newly created repo for standard PPX derivers that are yet to be consolidated, collected, or written | This repo will hold any Issues that are to be created during the project, and will contains any reimplemented derivers that are worked on. |
| [thierry-martinez/ppx_show](https://github.com/thierry-martinez/ppx_show "thierry-martinez/ppx_show") | The show deriver based on `ppxlib`| This implementation will be upstreamed to the new `standard_derivers` repo |
| [janestreet/ppx_compare](https://github.com/janestreet/ppx_compare "janestreet/ppx_compare") | Deriver equivalent to `eq` and `ord`, with dependency on `base` | This implementation will be updated to no longer depend on `base` and to follow the larger ecosystem's syntax conventions, also to the new `standard_derivers` repo |
| [janestreet/ppx_fields_conv](https://github.com/janestreet/ppx_fields_conv "janestreet/ppx_fields_conv") | Deriver equivalent to `make`, `iter`, `map` and `fold` with dependency on `base` | Same as above |

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
- Find best times in the day to have fixed work hours, intersecting with CET
