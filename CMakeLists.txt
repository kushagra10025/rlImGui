###########
# rlImGui #
###########

cmake_minimum_required(VERSION 3.25)

project(rldearimgui)

set(RLIMGUI_SOURCES
    "${CMAKE_CURRENT_SOURCE_DIR}/rlImGui.cpp"
)

add_library(${PROJECT_NAME} STATIC ${RLIMGUI_SOURCES})
add_library(raylib::rldearimgui_static ALIAS ${PROJECT_NAME})

target_include_directories(${PROJECT_NAME}
	PUBLIC "${CMAKE_SOURCE_DIR}/external/raylib/src"
	PUBLIC "${CMAKE_SOURCE_DIR}/external/imgui/"
	INTERFACE "${CMAKE_CURRENT_SOURCE_DIR}"
)

install(TARGETS ${PROJECT_NAME})
