# `glslView-nvim`

When editing GLSL shaders,
  this plugin provides the command `GlslView` which will open 
  [glslViewer](https://github.com/patriciogonzalezvivo/glslViewer)
  to the file being edited in the current buffer.
It is opened with the `-l` flag so that `glslViewer` will automatically listen
  for file changes,
  updating the preview as you save.

## 📦 Installation
Install the plugin with your preferred package manager.
For example,
  in [packer](https://github.com/wbthomason/packer.nvim) simply:

```lua
  use { 'timtro/glslView-nvim', ft = 'glsl', config = require('glslView').setup }
```
Don't forget to `PackerCompile` after installation so that the plugin will only
  be loaded for glsl files.
You'll also need a plugin to detect the glsl filetype.
I use [vim-glsl](https://github.com/tikhomirov/vim-glsl) which also provides
  syntax highlighting.

#### Installing `glslViewer`
See [installation](https://github.com/patriciogonzalezvivo/glslViewer/wiki/Installing)
  in the glslViewer Wiki.


## ⚙️ Configuration
The only configuration currently available is setting the executable file path for glslViewer

This can be done by passing the `exe_path` option to `setup()`.
For example,
  in [packer](https://github.com/wbthomason/packer.nvim) simply:

```lua
  use {
    'timtro/glslView-nvim',
    ft = 'glsl',
    config = function()
      require('glslView').setup { exe_path = "/path/to/glslView.exe" }
    end
  }
```

## 💪 Usage
Simply use the command `:GlslView` to open the current buffer in glslViewer.

## 🧰 Alternatives
 * [vim-GlslViewer](https://github.com/patriciogonzalezvivo/vim-glslViewer) -
    Version drift seems to have rendered it useless (at this time) since it
    laucnes the process with `&` to free up the UI, but this causes glslViewer
    to stop rendering (and then in my case, close).
