# Handle JEMALLOC configuration
if(NOT DISABLE_JEMALLOC)
    if(JEMALLOC)
        add_definitions(-DROCKSDB_JEMALLOC)
    endif()

    if(JEMALLOC_INCLUDE)
        include_directories(${JEMALLOC_INCLUDE})
    endif()
endif()

add_executable(cloud_durable_example
        cloud_durable_example.cc)
target_link_libraries(cloud_durable_example
        ${ROCKSDB_LIB} ${AWSSDK_LINK_LIBRARIES})

add_executable(clone_example
        clone_example.cc)
target_link_libraries(clone_example
        ${ROCKSDB_LIB} ${AWSSDK_LINK_LIBRARIES})

add_executable(cloud_dump
        cloud_dump.cc)
target_link_libraries(cloud_dump
        ${ROCKSDB_LIB} ${AWSSDK_LINK_LIBRARIES})
