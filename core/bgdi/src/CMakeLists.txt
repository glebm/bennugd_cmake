add_definitions (-D__BGDI__)
add_definitions (-DDEBUG)

include_directories (
  ../include
  ../../include
  ../../bgdrtm/include
)

add_executable (
  bgdi
  main.c
)

if (USE_LIBDES)
  target_link_libraries (
    bgdi
    bgdrtm
    z
    des
  )
else ()
  target_link_libraries (
    bgdi
    bgdrtm
    z
    crypto
  )
endif ()

install (
  TARGETS
  bgdi
  DESTINATION
  /usr/bin
)