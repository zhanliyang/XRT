include_directories(
  ${CMAKE_CURRENT_SOURCE_DIR}/../include
  ${CMAKE_SOURCE_DIR}/runtime_src
  )

add_subdirectory(xmaplugin)
add_subdirectory(xmaapi)

find_library(XML2_LIB xml2)
find_path(XML2_LIB_INCLUDE libxml/parser.h libxml2)
if(NOT XML2_LIB_INCLUDE)
  message(ERROR ": xml2 headers not found")
  set(XML2_LIB_INCLUDE "/usr/include/libxml2")
  MESSAGE("xml2 include path: ${XML2_LIB_INCLUDE}")
endif()
