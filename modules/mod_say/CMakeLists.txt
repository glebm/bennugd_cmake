include_directories (
  ../../core/include
)

add_library (
  mod_say
  ${MODULES}
  mod_say.c
) 

target_link_libraries (
  mod_say
  bgdrtm
)

if (NOT STATIC_MODULES)
  install (
    TARGETS
    mod_say
    DESTINATION
    /usr/lib
  )
endif ()
