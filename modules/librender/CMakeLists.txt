add_definitions (-D__LIBRENDER)

include_directories (
  ../../core/include
  ../../core/bgdrtm/include
  ../libblit
  ../libvideo
  ../libgrbase
)

add_library (
  render
  ${MODULES}
  librender.c
  g_fade.c
  g_frame.c
  g_instance.c
  g_object.c
  g_rects.c
  g_screen.c
  scaler_hq2x.c
  scaler_normal.c
  scaler_scale2x.c
  scaler_scanline.c
) 

target_link_libraries (
  render
  SDL
  bgdrtm
  blit
  video
  grbase
)

if (NOT STATIC_MODULES)
  install (
    TARGETS
    render
    DESTINATION
    /usr/lib
  )
endif ()
