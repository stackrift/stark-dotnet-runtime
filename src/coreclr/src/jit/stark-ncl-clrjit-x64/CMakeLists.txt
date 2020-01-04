project(stark-ncl-clrjit-x64)

add_definitions(-DSTARK)
add_definitions(-DFEATURE_NO_HOST)
add_definitions(-DSELF_NO_HOST)
remove_definitions(-DFEATURE_MERGE_JIT_AND_ENGINE)
add_definitions(-D_TARGET_UNIX_)

if(FEATURE_READYTORUN)
  add_definitions(-DFEATURE_READYTORUN_COMPILER)
endif(FEATURE_READYTORUN)

add_definitions(-DUNIX_AMD64_ABI)
set(JIT_ARCH_SOURCES ${JIT_AMD64_SOURCES} ${JIT_STARK_SOURCES})
set(JIT_ARCH_LINK_LIBRARIES gcinfo)

add_jit(stark-ncl-clrjit-x64)

target_include_directories(stark-ncl-clrjit-x64 PRIVATE
    ${CMAKE_CURRENT_LIST_DIR}/..
    ${JIT_SOURCE_DIR}
)
