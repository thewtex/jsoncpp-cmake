set( json_SRCS
  json_reader.cpp
  json_value.cpp
  json_writer.cpp
  )
# Shared libraries on Windows are currently broken.
if( WIN32 )
  add_library( ${JsonCpp_LIBRARY} STATIC ${json_SRCS} )
else()
  add_library( ${JsonCpp_LIBRARY} ${json_SRCS} )
endif()
install( TARGETS json
  EXPORT JsonCppTargets
  ARCHIVE DESTINATION lib COMPONENT Development
  LIBRARY DESTINATION lib COMPONENT RuntimeLibraries
  )
