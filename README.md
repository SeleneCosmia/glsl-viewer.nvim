# `glsl-viewer.nvim`
<!--
When editing GLSL shaders,
  this plugin provides the command `GlslView` which will open 
  ![glslViewer][1]
  to the file being edited in the current buffer.
By default, it is opened with the `-l` flag so that `glslViewer` will automatically listen
  for file changes,
  updating the preview as you save.
-->
>[!NOTE]
>This plugin depends on ![glslViewer][1] being installed and in your `PATH` in order to work.

## Installation

TODO

## Configuration
Configuration is done by passing options to `setup()`. The defaults are:

```lua
require('glsl_viewer').setup {
  viewer_path = 'glslViewer',
  args = { '-l' },
}
```

## Usage
Use the command `:GlslView` to open the current buffer in glslViewer.

Additional arguments will be passed to the executable after any arguments set in configuration.

For example, to start with a 128x256 window:

```vimscript
:GlslView -w 128 -h 256
```
More primitively, one can call directly through Lua:
```
:lua require('glslView').glslView({'-w', '128', '-h', '256'})
```

[1]: https://github.com/patriciogonzalezvivo/glslViewer
