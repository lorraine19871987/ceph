add_library(ceph_example SHARED compressor_plugin_example.cc)

# unittest_compression_plugin
add_executable(unittest_compression_plugin EXCLUDE_FROM_ALL
  test_compression_plugin.cc
  )
add_ceph_unittest(unittest_compression_plugin ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/unittest_compression_plugin)
target_link_libraries(unittest_compression_plugin global)
add_dependencies(unittest_compression_plugin ceph_example)

# unittest_compression_snappy
add_executable(unittest_compression_snappy EXCLUDE_FROM_ALL
  test_compression_snappy.cc
  )
add_ceph_unittest(unittest_compression_snappy ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/unittest_compression_snappy)
target_link_libraries(unittest_compression_snappy global ceph_snappy)

# unittest_compression_plugin_snappy
add_executable(unittest_compression_plugin_snappy EXCLUDE_FROM_ALL
  test_compression_plugin_snappy.cc
  )
add_ceph_unittest(unittest_compression_plugin_snappy ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/unittest_compression_plugin_snappy)
target_link_libraries(unittest_compression_plugin_snappy global)
add_dependencies(unittest_compression_plugin_snappy ceph_snappy)

# unittest_compression_zlib
add_executable(unittest_compression_zlib EXCLUDE_FROM_ALL
  test_compression_zlib.cc
  )
add_ceph_unittest(unittest_compression_zlib ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/unittest_compression_zlib)
target_link_libraries(unittest_compression_zlib global ceph_zlib)

# unittest_compression_plugin_zlib
add_executable(unittest_compression_plugin_zlib EXCLUDE_FROM_ALL
  test_compression_plugin_zlib.cc
  )
add_ceph_unittest(unittest_compression_plugin_zlib ${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/unittest_compression_plugin_zlib)
target_link_libraries(unittest_compression_plugin_zlib global)
add_dependencies(unittest_compression_plugin_zlib ceph_zlib)
