set(SOURCES demo.cpp Simple_Apu.cpp Wave_Writer.cpp)

add_executable(demo)
target_sources(demo PRIVATE ${SOURCES})
target_include_directories(demo PRIVATE .)
target_link_libraries(demo PRIVATE nes-snd-emu::nes-snd-emu)

if(NOT MSVC)
	# Wave_Writer.cpp has an initializer list with a ton of narrowing
	# conversions.
	target_compile_options(demo PRIVATE -Wno-narrowing)
endif()

# Wave_Writer.cpp uses fopen.
target_compile_definitions(demo PRIVATE _CRT_SECURE_NO_WARNINGS)