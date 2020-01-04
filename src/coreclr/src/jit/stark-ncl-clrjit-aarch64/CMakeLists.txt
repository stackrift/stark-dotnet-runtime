project(stark-ncl-clrjit-aarch64)

add_definitions(-DSTARK)
add_definitions(-DFEATURE_NO_HOST)
add_definitions(-DSELF_NO_HOST)
remove_definitions(-DFEATURE_MERGE_JIT_AND_ENGINE)
add_definitions(-D_TARGET_UNIX_)

if(FEATURE_READYTORUN)
  add_definitions(-DFEATURE_READYTORUN_COMPILER)
endif(FEATURE_READYTORUN)

remove_definitions(-D_TARGET_AMD64_)
add_definitions(-D_TARGET_ARM64_)
set(JIT_ARCH_SOURCES ${JIT_ARM64_SOURCES} ${JIT_STARK_SOURCES})
set(JIT_ARCH_LINK_LIBRARIES gcinfo_arm64)

add_jit(stark-ncl-clrjit-aarch64)

target_include_directories(stark-ncl-clrjit-aarch64 PRIVATE
    ${CMAKE_CURRENT_LIST_DIR}/..
    ${JIT_SOURCE_DIR}
)
