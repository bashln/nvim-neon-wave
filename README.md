# nvim-neon-wave

Neon Wave for Neovim — a colorscheme generated from the palettes of
[100-themes](https://github.com/bjarneo/100-themes).

Ships five variants:

| Colorscheme | Background | Notes |
| --- | --- | --- |
| `neon-wave` | dark | the design palette |
| `neon-wave-day` | light | for bright rooms |
| `neon-wave-high-contrast` | dark | the six normal ANSI colors reach WCAG AAA |
| `neon-wave-day-high-contrast` | light | the six normal ANSI colors reach WCAG AAA |
| `neon-wave-oled` | pure black | panels stay off on OLED |

## Install

lazy.nvim:

```lua
{
  'bashln/nvim-neon-wave',
  priority = 1000,
  lazy = false,
  opts = {},
  config = function(_, opts)
    require('neon-wave').setup(opts)
    vim.cmd.colorscheme('neon-wave')
  end,
}
```

LazyVim — drop this in `lua/plugins/colorscheme.lua`:

```lua
return {
  {
    'bashln/nvim-neon-wave',
    priority = 1000,
    lazy = false,
    opts = {
      -- transparent = true,
      -- dim_inactive = true,
    },
    config = function(_, opts)
      require('neon-wave').setup(opts)
      vim.cmd.colorscheme('neon-wave')
    end,
  },
  {
    'LazyVim/LazyVim',
    opts = { colorscheme = 'neon-wave' },
  },
}
```

Then switch variants any time with `:colorscheme neon-wave-day`.

## Options

```lua
require('neon-wave').setup({
  transparent = false,
  dim_inactive = false,
  styles = {},
  on_highlights = nil,
  integrations = {},
  palette_overrides = {},
  terminal = true,
})
```

`transparent` applies to editor windows (`Normal`, `NormalNC`, `SignColumn`,
`FoldColumn`, `EndOfBuffer`). Floats and popups keep their background for
readability.

## Health

```
:checkhealth neon-wave
```

## License

MIT
