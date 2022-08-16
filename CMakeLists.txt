cmake_minimum_required(VERSION 3.18)
project(MiisendU-Wii-U)

add_executable(MiisendU-Wii-U
    source/main.c
    source/screen_utils.c
    source/udp.c
    source/vpad_to_json.cpp
    source/vendor/inih/ini.c
)

include_directories(SYSTEM
    source/vendor/inih
)

target_include_directories(MiisendU-Wii-U PUBLIC
    ${DEVKITPRO}/portlibs/ppc/include
)

target_link_libraries(MiisendU-Wii-U
    jansson
)

wut_create_rpx(MiisendU-Wii-U)
