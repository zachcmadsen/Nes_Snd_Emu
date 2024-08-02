cmake_minimum_required(VERSION 3.27)

project(
    nes-snd-emu
    VERSION 0.1.0
)

add_subdirectory(src)

if(CMAKE_CURRENT_SOURCE_DIR STREQUAL CMAKE_SOURCE_DIR)
    option(NES_SND_EMU_BUILD_DEMO "Build Nes_Snd_Emu demo program" ON)

    if(NES_SND_EMU_BUILD_DEMO)
		add_subdirectory(demo)
	endif()
endif()