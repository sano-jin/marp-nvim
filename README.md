# 🔌 Marp.nvim

A [neovim](https://neovim.io/) plugin for [Marp](https://marp.app/).

## ✨ Features

- start/stop the Marp server
- toggle the Marp server (start/stop)
- see if Marp server is running
- browser window opens when Marp is running and ready

## ⚡️ Requirements

- [Marp](https://marp.app/) CLI installed and available in your path

## 📦 Installation

Install the plugin with your preferred package manager:

Packer:

```lua
  use({
    "mpas/marp-nvim",
  }),
```

Lazy:

```lua
  {
    "mpas/marp-nvim",
  },
```

With a specific configuration:

```lua
  {
    "mpas/marp-nvim",
    config = function()
      require("marp").setup({
        port = 8080,
        wait_for_response_timeout = 30,
        wait_for_response_delay = 1,
      })
    end,
  },
```

## ⚙️ Configuration

The following defaults are provided:

```lua
{
  port = 8080, -- the port on which the Marp server should listen
  wait_for_response_timeout = 30, -- how long to wait for a response from the server before giving up
  wait_for_response_delay = 1, -- how long to wait between attempts to connect to the server
  cli_options = "", -- some extra command line arguments for the marp-cli
}
```

In the above example, the Marp server will be started on port 8080, and the plugin will wait for up to 30 seconds for a response from the server before giving up. It will try to connect to the server every second. No extra command line arguments are passed to the marp-cli.

## ⌨️ Keybindings

This plugin does not set any keybindings by default. You can set them yourself like this:

```lua
vim.keymap.set("n", "<leader>MT", "<cmd>MarpToggle<cr>", { noremap = true, silent = true })
vim.keymap.set("n", "<leader>MS", "<cmd>MarpStatus<cr>", { noremap = true, silent = true })
...
```

The following commands are available:

- `:MarpStart` - start the Marp server
- `:MarpStop` - stop the Marp server
- `:MarpToggle` - toggle the Marp server (start/stop)
- `:MarpStatus` - see if Marp server is running

## 💡Inspiration

This plugin is inspired by [aca/marp.nvim](https://github.com/aca/marp.nvim)!
