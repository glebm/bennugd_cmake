include_directories (
  ../../core/include
  ../../core/bgdrtm/include
)

add_library (
  wm
  ${MODULES}
  libwm.c
) 

target_link_libraries (
  wm
  SDL
  bgdrtm
)

if (NOT STATIC_MODULES)
  install (
    TARGETS
    wm
    DESTINATION
    /usr/lib
  )
endif ()
