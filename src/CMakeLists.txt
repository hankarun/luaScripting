add_executable(game 
	main.cpp
	imgui_impl_dx11.cpp
	imgui_impl_dx11.h
	imgui_impl_win32.cpp
	imgui_impl_win32.h
)

target_link_libraries(game PRIVATE
  lua::lua
  sol2::sol2
  imgui::imgui
  d3d11 d3dcompiler dxgi
)

set_property(TARGET game PROPERTY CXX_STANDARD 17)
