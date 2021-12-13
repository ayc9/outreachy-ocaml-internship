This post is aimed toward OCaml users who are interested in writing their own rewriters.
It gives an overview of the PPX ecosystem as of 2019.
Defining pre-processors as functions that operate on the AST generated from a user's code and return a new AST.
In the case of OCaml, the AST is a set of recursive types. (see Discuss post)
The AST is what is passed to the compiler to be type checked and compiled to native code.
The recursive types are defined in OCaml's `Parsetree` module. Some of these types include:
    - `structure` which describes the content of an `.ml` file;
    - `signature` which descirbes the content of an `.mli` file.

Writing a rewriter requires users to understand the AST.
Start with `Parsetree` module to understand AST, as well as comments in `parsetree.mli` here: https://github.com/ocaml/ocaml/blob/trunk/parsing/parsetree.mli
Another tool is `dumpast` that pretty prints ASTs given valid OCaml code.
Try these three tools to print AST
    Note that you can use the compiler or utop have a similar feature with the -dparsetree flag. Running ocamlc/ocamlopt -dparsetree file.ml will pretty print the AST of the given file while running utop -dparsetree will pretty print the AST of the evaluated code alongside it's evaluation. I tend to prefer the pretty printed AST from dumpast but any of these tools will prove helpful in understanding the AST representation of a given piece of OCaml code.

Language extensions
    Extension nodes
        are used in place of ----
        /!\ Don't understand this example.
    Attributes
        Attributes are attached to existing AST nodes instead of replacing them like extension nodes.

Rewriters
    Extensions
    Derivers

How to write a PPX using ppxlib
    - ppxlib gives tool to write and work with extensions
    - `Ast_pattern`
    /!\ how important is it for me to understand the above? ^
    - Writing a deriver

Deriver attributes: optional `attributes` parameter
    lets you define which attributes your deriver allows the user to attach to various bits to whatever it's applied to

Writing  expand functions

Handling `location`

Reporting errors from your rewriter 

TESTING
