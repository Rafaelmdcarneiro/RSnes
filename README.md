# rsnes

<div align='center'>
  <img src='https://user-images.githubusercontent.com/26610181/131219139-4b2c12ca-cc3d-4a72-827c-1c83476a4401.png'
       alt='rsnes logo' width='384cm' align='center'>
</div>

A [SNES](https://en.wikipedia.org/wiki/Super_Nintendo_Entertainment_System)
emulator written in [Rust](https://www.rust-lang.org/)

## Implementation Status

Many games are already playable, but some graphics and sounds are faulty.
Comparatively functioning games are e.g. Donkey Kong Country, Wolfenstein 3D,
F-Zero, Super Mario World, Super Mario Kart, The Legend of Zelda,
Super Street Fighter II.

## Usage

In the default configuration, controller port 1 is connected to a
standard controller and port 2 is left unconnected.
These keyboard keys will drive controller 1:

| Keyboard key on QWERTY | Controller key       |
|------------------------|----------------------|
| **W**                  | **↑**                |
| **A**                  | **←**                |
| **S**                  | **↓**                |
| **D**                  | **→**                |
| **Q**                  | **L**                |
| **E**                  | **R**                |
| **Left Alt**           | **Start**            |
| **Right Alt**          | **Select**           |
| **J**                  | **A**                |
| **K**                  | **B**                |
| **L**                  | **X**                |
| **;** *\**             | **Y**                |
| 0-9                    | Store Save State 0-9 |
| Shift + 0-9            | Load Save State 0-9  |

*\** the button right of *L*

## Configuration

You can configure rsnes with a [TOML](https://toml.io/) configuration file.
You can provide this file by using the option `--config <PATH>` or by placing
it into one of these paths:

- `$HOME/.config/rsnes/config.toml`
- `$HOME/.config/rsnes.toml`
- `/etc/rsnes.toml`

See `emulator/example.toml` for
[documentation](https://github.com/nat-rix/rsnes/blob/main/emulator/example.toml).

## Structure

This repository is a workspace consisting of two crates

- `rsnes` - the SNES backend library (located in `/rsnes/`)
- `rsnes-emulator` - a sample frontend implementation using `winit` and `wgpu`
  (located in `/emulator/`)

⚠️ Please note that the `rsnes` API is neither tested nor documented (well) ⚠️

⚠️ Also note, that `rsnes-emulator` is only tested on Linux/X11 ⚠️

## Features

This is a set of features to be implemented in the future (sorted by priority)

- [x] Mode 7 support
- [x] Sprite support
- [x] Color math
- [x] S-DSP echo effect support
- [x] S-DSP noise effect support
- [x] PPU Mosaic effect
- [ ] Save game to files
- [ ] SA-1 support
- [ ] Real gamepad input support for `rsnes-emulator`
      (see [winit#944](https://github.com/rust-windowing/winit/issues/944),
      maybe use unstable fork or branch?)
- [ ] Improved documentation
- [ ] Tests
  - [ ] 65816 processor instruction tests
  - [ ] SPC-700 processor instruction tests
  - [ ] Audio tests
  - [ ] Video output tests
- [ ] configurable UI
  - [x] configurable key bindings
- [ ] emulator running also on [WASM](https://webassembly.org/)
- [x] [DSP](https://en.wikipedia.org/wiki/NEC_%C2%B5PD7720#%C2%B5PD77C25)
      coprocessor support
  - [x] DSP-1, DSP-1A, DSP-1B
  - [x] DSP-2, DSP-3, DSP-4 (low priority)
  - [ ] ST010, ST011 (very low priority)
- [ ] [GSU](https://en.wikipedia.org/wiki/Super_FX) coprocessor support
      (also known as Super FX)
  - [ ] GSU1
  - [ ] GSU2
- [x] Complete the 65816 instruction set
- [x] Complete the SPC700 instruction set
- [x] Complete the NEC μPD77C25 instruction set
- [ ] Complete the GSU instruction set
- [ ] Multitap (MP5) controller support
- [x] [SNES Mouse](https://en.wikipedia.org/wiki/Super_NES_Mouse) support
- [ ] [SNES Super Scope](https://en.wikipedia.org/wiki/Super_Scope) support
- [x] Save States
- [ ] Capcom CX4 coprocessor support
      (this processor is only used in Mega Man X2 and Mega Man X3)
- [ ] SPC7110 data decompression chip

## Contributing

Contributions of any kind (bug reports, feature requests, pull requests, …) are
very welcome.
