## Week 2: 2021-12-13 to 2021-12-17

The second week saw work starting on a new deriver, the `make` deriver, as well as the first publication of a blog.

### Blog
A home page and a first blog post were published on 12-14; [read the blog here](https://outreachyxocaml.wordpress.com/).

The homepage covers what Outreachy and OCaml are, and the first post covers some resources to learn about PPX.

Outreachy recommends writing a post every two weeks, but mentors agreed once a month might be enough.

### Plan for a `make` deriver
`make` was chosen to be the first deriver to work on for the following reasons:
- It only acts on one type: records
- It only derives one function: a `make` function that takes some fields and returns a record

The main task is to extract `create` from [this `ppx_fields_conv` repo](https://github.com/janestreet/ppx_fields_conv) that covers a whole module with multiple derivers (`map`, `fold`, `iter`...). "Extracting" means selecting what we are interested in from the existing code into [this new repo for `standard_derivers`](https://github.com/ayc9/standard_derivers/tree/main).

The work of week 2 can be tracked on [this fork of `ppx_fields_conv`](https://github.com/ayc9/ppx_fields_conv/tree/create). 

By the end of week 2, the `create` branch linked above had:
- removed most of the unneeded code that derived the other functions like `map` 
- refactored to remove module creation so that the deriver only generates 1 function
- added a test for `create` following how tests were done in the original `ppx_conv_fields` using `test_inline`

### Pairing notes
Week 2 had 3 pairing sessions!
- Wednesday with Patrik on OCaml basics; notes here.
- Thursday with Sonja on the `fields_conv` code and the subsequent bug, notes here.
- Friday with Shon on that same bug that was due to the local environment and whose fix covered `opam` basics, notes here.

### General OCaml progress
Sonja shared a great lecture that goes over PPX and the "new" way to do them. [Find it here](https://www.youtube.com/watch?v=dMoRMqQ6GLs&t=4206s&ab_channel=ReasonConf)!
