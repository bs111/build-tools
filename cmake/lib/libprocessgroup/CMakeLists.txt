cmake_minimum_required(VERSION 3.4.1)

project(libprocessgroup)


set(LIBPROCESSGROUP ${CMAKE_SOURCE_DIR}/${AOSP}/system/core/libprocessgroup)


set(LIBPROCESSGROUP_SRC_FILES
	${LIBPROCESSGROUP}/cgroup_map.cpp
    ${LIBPROCESSGROUP}/processgroup.cpp
    ${LIBPROCESSGROUP}/sched_policy.cpp
    ${LIBPROCESSGROUP}/task_profiles.cpp
	)


include_directories(
	${libprocessgroup_headers}
	${libcutils_headers}
	${libbase_headers}
	${libjsoncpp_headers}
	)

set(CMAKE_CXX_FLAGS "${GLOBAL_CXX_FLAGS} -Wexit-time-destructors")

add_library(processgroup STATIC ${LIBPROCESSGROUP_SRC_FILES})
target_link_libraries(processgroup)

