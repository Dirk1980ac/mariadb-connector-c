SET(PLUGIN_EXTRA_FILES ${CC_SOURCE_DIR}/libmariadb/ma_errmsg.c)


FILE(GLOB plugin_dirs ${CC_SOURCE_DIR}/plugins/*)
FOREACH(dir ${plugin_dirs})
  IF (EXISTS ${dir}/CMakeLists.txt)
    MESSAGE(STATUS "processing ${dir}")
    INCLUDE(${dir}/CMakeLists.txt)
  ENDIF()
ENDFOREACH()
