set( json_SRCS
  json_reader.cpp
  json_value.cpp
  json_writer.cpp
  )
# Shared libraries on Windows are currently broken.
if( WIN32 )
  add_library( jsoncpp STATIC ${json_SRCS} )
else()
  add_library( jsoncpp ${json_SRCS} )
endif()
install( TARGETS jsoncpp
  ARCHIVE DESTINATION lib COMPONENT Development
  LIBRARY DESTINATION lib COMPONENT RuntimeLibraries
  )
