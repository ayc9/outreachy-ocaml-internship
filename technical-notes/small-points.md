Below is a list of small things worth taking note of:
- In `ppxlib`
    - Documentation/code comment for use of `add` in `Deriving` lists all optional items without clarifying having to use at least 1.
- In `ppx_show`
    - Explicitly specifying `Ppxlib.Deriving` even after module is opened: `open ppxlib`
