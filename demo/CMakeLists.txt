add_executable(demo)
target_sources(
	demo PRIVATE
	demo.cpp
	Simple_Apu.cpp
	Wave_Writer.cpp
)
target_include_directories(demo PRIVATE .)
target_link_libraries(demo PRIVATE nes-snd-emu::nes-snd-emu)

if(MSVC)
	# Wave_Writer.cpp uses fopen.
	target_compile_definitions(demo PRIVATE _CRT_SECURE_NO_WARNINGS)
else()
	# Wave_Writer.cpp has an initializer list with a lot of narrowing
	# conversions.
	target_compile_options(demo PRIVATE -Wno-narrowing)
endif()