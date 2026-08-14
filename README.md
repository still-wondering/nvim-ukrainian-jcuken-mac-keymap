
# Ukrainian Neovim keymap for Apple keyboard

New Apple MacBooks and probably other Apple keyboards have new and a bit different layout than 
other or older Apple keyboards. This includes changed positions of buttons:
- `ґ` (`` ` `` on English layout)
- `Ґ` (`~` on English layout)
- `\` (`§` on English layout)
- `/` (`±` on English layout)
- `ʼ` `\` on English layout)
- `₴` (`|` on English layout)

This keymap allows to have all Ukrainian symbols as on the Apple keyboard layout.

Also, quickly typing `\\` (in Ukrainian layout) would insert an accent sign on the previous letter, like `а́`.


## Installation

### vim.pack

```lua
vim.pack.add{ 'hrycko-mb/nvim-ukrainian-jcuken-mac-keymap' }
```


### Manually

You can install this keymap manually, by putting `keymap/ukrainian-jcuken-mac.vim` into your 
configuration path (by default `~/.config/nvim`) as `~/.config/nvim/keymap/ukrainian-jcuken-mac.vim`.


## Usage

To activate the keymap add the following configuration to your lua config:
```lua
vim.o.keymap = 'ukrainian-jcuken-mac' -- sets the actual keymap
vim.o.spelllang = 'ua' -- sets spell checking language (requires spell file)
vim.cmd 'language uk_UA.UTF-8' -- sets Neovim language (useful when you don't have Ukrainian locale)
```


Or set up commands to switch between languages. For example:
```lua
vim.api.nvim_create_user_command('UA', function()
  vim.o.keymap = 'ukrainian-jcuken-mac'
  vim.o.spelllang = 'ua'
  vim.cmd 'language uk_UA.UTF-8'
end, {})

vim.api.nvim_create_user_command('EN', function()
  vim.o.keymap = ''
  vim.o.spelllang = 'en_us'
  vim.cmd 'language en_US.UTF-8'
end, {})
```

See documentation for more: \
<https://neovim.io/doc/user/usr_45.html#_language-for-messages> \
<https://neovim.io/doc/user/options.html#'keymap'>  \
<https://neovim.io/doc/user/options.html#'spelllang'>

