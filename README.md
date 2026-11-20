# dredge.nvim

A quiet Neovim colorscheme, dark and light: three hues in code, and the names
stay plain.

| Role      | Colour | Covers                                           |
| --------- | ------ | ------------------------------------------------ |
| Name      | plain  | variables, functions, calls, members, parameters |
| Keyword   | violet | every keyword, and markup tags                   |
| Type      | teal   | type names                                       |
| Literal   | olive  | strings, numbers, booleans                       |
| Structure | grey   | operators, brackets, delimiters                  |
| Comment   | grey   | comments and docstrings                          |

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

The plugin ships `after/queries/<language>/highlights.scm` files that add
role captures stock queries do not make (`@variable.write`, `@keyword.exit`,
`@declaration.*` and a few more) for bash,
C#, CSS, JavaScript, Go, Jinja, Python, Rust, SCSS, SQL, TypeScript, Vue and
YAML. They extend the stock queries, so they stay loaded under any colorscheme;
one that does not define these groups ignores them.

## lualine

A `dredge` lualine theme ships with the plugin; `theme = "auto"` picks it up.
