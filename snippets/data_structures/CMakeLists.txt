add_executable(sequential_containers sequential_containers.cpp)

add_executable(associative_containers associative_containers.cpp)

find_package(PMR)
if (PMR_FOUND)
    add_executable(memory_resource memory_resource.cpp)
else ()
    message("Your compiler does not support *PMR* yet")
endif ()

add_executable(span span.cpp)

add_executable(tuples tuples.cpp)

add_executable(variant variant.cpp)

add_executable(any any.cpp)

add_executable(bitset bitset.cpp)

add_executable(optional optional.cpp)

FetchContent_Declare(pareto GIT_REPOSITORY https://github.com/alandefreitas/pareto.git GIT_TAG v1.2.0)
FetchContent_MakeAvailable(pareto)
add_executable(spatial_containers spatial_containers.cpp)
target_link_libraries(spatial_containers PUBLIC pareto)