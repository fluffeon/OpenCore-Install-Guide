# Fixing Resolution and Verbose

* Supported version: 0.5.8

Wanting a more clean booting experience with macOS without all that verbose text while booting? Well you need a couple things:

## Recommended Configuration

**`Misc -> Debug`**

* Set `AppleDebug` to False, this will remove boot.efi debugging right at the start of booting.

**`NVRAM -> Add -> 7C436110-AB2A-4BBB-A880-FE41995C9F82 -> boot-args`**:

* Remove `-v` from your config.plist

**`NVRAM -> Add -> 4D1EDE05-38C7-4A6A-9CC6-4BCCA8B38C14 -> UIScale`**:

* `01`: Standard resolution
* `02`: HiDPI (generally required for FileVault to function correctly on smaller displays)

**`UEFI -> Output`**:

* `TextRenderer` set to`BuiltinGraphics`
* `Resolution`: set to `Max` for best results
  * Optionally can specify resolution: `WxH@Bpp (e.g. 1920x1080@32) or WxH (e.g. 1920x1080)`
* `ProvideConsoleGop` set to True

If still having issues, see [Configuration.pdf](https://github.com/acidanthera/OpenCorePkg/blob/master/Docs/Configuration.pdf) for all possible options.