add_subdirectory(apphost)
add_subdirectory(dotnet)
add_subdirectory(fxr)
add_subdirectory(hostpolicy)
add_subdirectory(nethost)
add_subdirectory(test_fx_ver)

add_subdirectory(test)

if(WIN32)
    add_subdirectory(comhost)
    add_subdirectory(ijwhost)
    add_subdirectory(winrthost)
endif()
