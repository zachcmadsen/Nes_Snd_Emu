cmake_minimum_required(VERSION 3.27)

project(nes-snd-emu)

option(NES_SND_EMU_BUILD_DEMO "Build Nes_Snd_Emu demo program" OFF)

add_subdirectory(src)

if(NES_SND_EMU_BUILD_DEMO)
	add_subdirectory(demo)
endif()