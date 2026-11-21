# dredge.nvim

A quiet Neovim colorscheme, dark and light: a few hues in code, and the names
stay plain.

| Role       | Colour    | Covers                                      |
| ---------- | --------- | ------------------------------------------- |
| Name       | plain     | variables, calls, members, parameters       |
| Definition | blue      | function and class names where defined      |
| Type       | teal      | type names                                  |
| Literal    | mustard   | strings, numbers, booleans, markup headings |
| Keyword    | olive     | keywords, markup tags                       |
| Operator   | wine      | operators, string escapes                   |
| Structure  | grey      | brackets, commas, dots, colons              |
| Comment    | blue-grey | comments and docstrings                     |
| Link       | violet    | markup links                                |
| TODO       | pink      | TODO tags in comments: bold text, no fill   |

Dark and light use the same roles.

Inspired by [solarized-osaka](https://github.com/craftzdog/solarized-osaka.nvim),
[flexoki](https://github.com/kepano/flexoki) and
[papercolor](https://github.com/NLKNguyen/papercolor-theme), on a deep teal
ground in dark and a cream ground in light. No italics.

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
