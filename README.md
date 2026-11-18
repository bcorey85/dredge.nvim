# dredge.nvim

A Neovim colorscheme, dark and light, that colours the **structure** of code
and leaves the names plain.

| Role      | Colour  | Covers                                                         |
| --------- | ------- | -------------------------------------------------------------- |
| Name      | plain   | variables, functions, calls, members, parameters               |
| Declare   | violet  | `function`, `local`, `class`, `import`, modifiers, markup tags |
| Flow      | blue    | `if`, `for`, `while`, `try`, and type names                    |
| Structure | teal    | operators, brackets, delimiters                                |
| Write     | orange  | a store into something that already exists                     |
| Exit      | magenta | `return`, `raise`, `break`, `continue`                         |
| Literal   | olive   | strings, numbers, booleans                                     |
| Comment   | yellow  | comments and docstrings                                        |

Inspired by [solarized-osaka](https://github.com/craftzdog/solarized-osaka.nvim),
[flexoki](https://github.com/kepano/flexoki) and
[papercolor](https://github.com/NLKNguyen/papercolor-theme), on a neutral
graphite ground. No italics.

Pure Lua, no dependencies, no `setup()`.

## Install

lazy.nvim:

```lua
{ "bcorey85/dredge.nvim", lazy = false, priority = 1000 }
```

## Use

```vim
colorscheme dredge
```

`dredge` follows `background`: `:set background=light` gives the light variant.

## Tree-sitter queries

Writes and exits are not captures that stock queries make. The plugin
ships `after/queries/<language>/highlights.scm` files that add them
(`@variable.write`, `@keyword.exit`, `@declaration.*` and a few more) for bash,
C#, CSS, JavaScript, Go, Jinja, Python, Rust, SCSS, SQL, TypeScript, Vue and
YAML. They extend the stock queries, so they stay loaded under any colorscheme;
one that does not define these groups ignores them.

## lualine

A `dredge` lualine theme ships with the plugin; `theme = "auto"` picks it up.
