cmake_minimum_required(VERSION 2.8)
set(CMAKE_DISABLE_SOURCE_CHANGES ON)
set(CMAKE_DISABLE_IN_SOURCE_BUILD ON)

include_directories(${CMAKE_SOURCE_DIR}/include)
include_directories(${CMAKE_CIRRENT_SOURCE_DIR})

# bandwidth_test
add_executable(bandwidth_test bandwidth_test.cpp aggregate_bandwidth.cpp partial_senders_allocator.cpp)
target_link_libraries(bandwidth_test derecho)

# latency_test
add_executable(latency_test latency_test.cpp aggregate_latency.cpp)
target_link_libraries(latency_test derecho)

# cooked send bandwidth test
add_executable(typed_subgroup_bw_test typed_subgroup_bw_test.cpp bytes_object.cpp)
target_link_libraries(typed_subgroup_bw_test derecho)

# persistent bandwidth
add_executable(persistent_bw_test persistent_bw_test.cpp aggregate_bandwidth.cpp partial_senders_allocator.cpp bytes_object.cpp)
target_link_libraries(persistent_bw_test derecho)

# persistent latency
add_executable(persistent_latency_test persistent_latency_test.cpp aggregate_latency.cpp partial_senders_allocator.cpp bytes_object.cpp)
target_link_libraries(persistent_latency_test derecho)

# signed log bandwidth
add_executable(signed_bw_test signed_bw_test.cpp aggregate_bandwidth.cpp partial_senders_allocator.cpp bytes_object.cpp)
target_link_libraries(signed_bw_test derecho)

add_executable(signed_store_test signed_store_test.cpp aggregate_bandwidth.cpp)
target_link_libraries(signed_store_test derecho)
