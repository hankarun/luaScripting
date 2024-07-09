### lua
add_library(lua
  lua/lapi.c
  lua/lauxlib.c
  lua/lbaselib.c
  lua/lcode.c
  lua/lcorolib.c
  lua/lctype.c
  lua/ldblib.c
  lua/ldebug.c
  lua/ldo.c
  lua/ldump.c
  lua/lfunc.c
  lua/lgc.c
  lua/linit.c
  lua/liolib.c
  lua/llex.c
  lua/lmathlib.c
  lua/lmem.c
  lua/loadlib.c
  lua/lobject.c
  lua/lopcodes.c
  lua/loslib.c
  lua/lparser.c
  lua/lstate.c
  lua/lstring.c
  lua/lstrlib.c
  lua/ltable.c
  lua/ltablib.c
  lua/ltests.c
  lua/ltm.c
  lua/lua.c
  lua/lundump.c
  lua/lutf8lib.c
  lua/lvm.c
  lua/lzio.c
)
add_library(lua::lua ALIAS lua)

if (WIN32)
  target_compile_definitions(lua PRIVATE LUA_USE_WINDOWS)
endif()

target_include_directories(lua PUBLIC lua)
if (UNIX)
  target_compile_definitions(lua PRIVATE LUA_USE_LINUX)
  target_link_libraries(lua PRIVATE dl)
endif()

### sol2
set(SOL2_LUA_VERSION "5.4.4" CACHE STRING "The version of Lua used")
# we build Lua manually
set(SOL2_BUILD_LUA FALSE CACHE BOOL "Always build Lua, do not search for it in the system")
add_subdirectory(sol2)


add_library(imgui
	imgui/imgui.cpp
	imgui/imgui_demo.cpp
	imgui/imgui_draw.cpp
	imgui/imgui_tables.cpp
	imgui/imgui_widgets.cpp
	imgui/imgui_stdlib.cpp
)
add_library(imgui::imgui ALIAS imgui)
target_include_directories(imgui PUBLIC imgui)
