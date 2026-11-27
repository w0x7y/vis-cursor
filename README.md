# vis-cursor

mode-dependent terminal cursor shapes for [vis](https://github.com/martanne/vis), like neovim: block in normal mode, bar in insert mode, underline in visual, replace and operator-pending mode

### install

needs a vis build after `0.9` (one with `vis.ui.style_ids` that moves the terminal's own cursor to the primary cursor) and a terminal that understands DECSCUSR (`\e[N q`). on `0.9` it loads as a no-op

```sh
git clone https://github.com/w0x7y/vis-cursor ~/.config/vis/plugins/vis-cursor
```

then in `visrc.lua`:

```lua
require("plugins/vis-cursor")
```

### config

DECSCUSR shape numbers: `2` block, `4` underline, `6` bar (or `1`, `3`, `5` for blinking)

```lua
local cursor = require("plugins/vis-cursor")
cursor.shapes[vis.modes.INSERT] = 5 -- blinking bar
```

resets the terminal cursor to its default (`\e[0 q`) on quit

_license: [mit](./LICENSE)_
