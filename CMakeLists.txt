cmake_minimum_required(VERSION 3.0.0)
project(libnice-tutorial-1 VERSION 0.1.0)


set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED on)

include(CTest)
enable_testing()

include_directories(/usr/include/glib-2.0
                    /usr/lib64/glib-2.0/include
                    /home/ysh8361/libnice/agent
                    /home/ysh8361/libnice/nice
                    /home/ysh8361/libnice/socket
                    /home/ysh8361/libnice/random)
                    
# link_directories(/home/ysh8361/workspace/c/libnice-tutorial-1/build)
link_directories(/home/ysh8361/libnice/builddir/nice)
link_libraries(pthread                
                nice_2
                 gthread-2.0
                 gio-2.0
                 gobject-2.0
                 glib-2.0 )
add_executable(libnice-tutorial-1 main.cpp)
add_executable(libnice-tutorial-2 main2.cpp)
add_executable(libnice-tutorial-3 main3.cpp)
add_executable(libnice-tutorial-3-backup main3-backup.cpp)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
