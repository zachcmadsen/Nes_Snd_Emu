add_library(nes-snd-emu)
add_library(nes-snd-emu::nes-snd-emu ALIAS nes-snd-emu)
target_sources(
	nes-snd-emu PRIVATE
	Blip_Buffer.cpp
	Nes_Apu.cpp
	Nes_Oscs.cpp
)
target_include_directories(nes-snd-emu SYSTEM INTERFACE .)