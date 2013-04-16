# For build tree configuration.
export( TARGETS ${JsonCpp_LIBRARY}
  FILE ${JsonCpp_BINARY_DIR}/JsonCppTargets.cmake )
set( JsonCpp_INCLUDE ${JsonCpp_SOURCE_DIR}/include )
configure_file( "${JsonCpp_SOURCE_DIR}/cmake/JsonCppConfig.cmake.in"
  "${JsonCpp_BINARY_DIR}/JsonCppConfig.cmake"
  @ONLY
  )

# For install configuration.
set( JsonCpp_INCLUDE "\${config_dir}/../../../include" )
configure_file( "${JsonCpp_SOURCE_DIR}/cmake/JsonCppConfig.cmake.in"
  "${JsonCpp_BINARY_DIR}/${CMAKE_FILES_DIRECTORY}/JsonCppConfig.cmake"
  @ONLY
  )
install(FILES
  "${JsonCpp_BINARY_DIR}/${CMAKE_FILES_DIRECTORY}/JsonCppConfig.cmake"
  DESTINATION lib/CMake/JsonCpp
  COMPONENT Development
  )
install(EXPORT JsonCppTargets
  DESTINATION lib/CMake/JsonCpp
  COMPONENT Development
  )
