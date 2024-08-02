# Nes_Snd_Emu

A stripped down fork of blargg's [Nes_Snd_Emu][nes_snd_emu].

The differences from the original are

- 2A03 APU emulation only
- CMake support
- no platform specific code or "blargg" headers
- updated[^1] source files from [DeaDBeeF][deadbeef]

## Documentation

The [documentation][nes_snd_emu] from the original library is still relevant. The files `readme.txt`, `notes.txt`, and `usage.txt` are good places to start.

See [demo][demo] for an example program.

## Usage

Include `Nes_Snd_Emu` with CMake's `FetchContent`:

```cmake
include(FetchContent)
FetchContent_Declare(
    nes-snd-emu
    URL https://github.com/zachcmadsen/Nes_Snd_Emu/releases/download/v0.1.0/nes-snd-emu-src.tar.gz
)
FetchContent_MakeAvailable(nes-snd-emu)

add_executable(nes-snd-emu-example)
target_sources(nes-snd-emu-example PRIVATE main.cpp)
target_link_libraries(nes-snd-emu-example PRIVATE nes-snd-emu::nes-snd-emu)
```

[^1]: The sources in DeaDBeef's version of Game_Music_Emu have more functionality than the ones in
Nes_Snd_Emu v0.1.7. I don't know if blargg actually intended for them to be updated verions.

[nes_snd_emu]: https://www.slack.net/~ant/libs/audio.html#Nes_Snd_Emu
[deadbeef]: https://github.com/DeaDBeeF-Player/deadbeef/tree/master/plugins/gme/game-music-emu-0.6pre
[demo]:https://github.com/zachcmadsen/Nes_Snd_Emu/tree/main/demo