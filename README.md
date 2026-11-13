# dredge.nvim

A Neovim colorscheme, dark and light, that colours syntax by what a token
**does**, not what it is.

| Role    | Colour  | Covers                                                                   |
| ------- | ------- | ------------------------------------------------------------------------ |
| Bind    | violet  | a name where it is introduced: function, class, variable, parameter, key |
| Read    | plain   | every later use of a name                                                |
| Call    | teal    | calls, decorators, constructors, builtins                                |
| Write   | orange  | a store into something that already exists                               |
| Exit    | magenta | `return`, `raise`, `break`, `continue`                                   |
| Literal | olive   | strings, numbers, booleans                                               |
| Type    | blue    | type names                                                               |
| Keyword | grey    | everything else the language reserves                                    |
| Comment | yellow  | comments and docstrings                                                  |

The hues are [solarized-osaka](https://github.com/craftzdog/solarized-osaka.nvim)'s,
on a slate ground. No italics.

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

Binds, writes and exits are not captures that stock queries make. The plugin
ships `after/queries/<language>/highlights.scm` files that add them
(`@declaration.*`, `@variable.write`, `@keyword.exit` and a few more) for bash,
C#, CSS, JavaScript, Go, Jinja, Python, Rust, SCSS, SQL, TypeScript, Vue and
YAML. They extend the stock queries, so they stay loaded under any colorscheme;
one that does not define these groups ignores them.

## lualine

A `dredge` lualine theme ships with the plugin; `theme = "auto"` picks it up.
