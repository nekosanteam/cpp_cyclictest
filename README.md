# README.md

  toolchain の指定
    cmake -DCMAKE_TOOLCHAIN_FILE=../cmake/gcc.cmake -G Ninja ..
    (ほとんどは gcc か clang を指定。)

  for debug:
    cmake -DCMAKE_BUILD_TYPE=Debug -G Ninja
    -> CMAKE_{C,CXX}_FLAGS_DEBUG  "-g "

  for release:
    cmake -DCMAKE_BUILD_TYPE=Release -G Ninja
    -> CMAKE_{C,CXX}_FLAGS_RELEASE "-O3 -DNDEBUG "

  cmake -j --build . 

  for multi-config:
    cmake -DCMAKE_CONFIGURATION_TYPES="Debug;Release" -G "Visual Studio 16 2019" -A x64
    cmake --build --config Debug .
    // VS の場合、CMAKE_GENERATOR_PLATFORM をセット。-A で指定。

　target の指定
    cmake --build --target Target .
    add_custom_target()

add_custom_command, add_custom_target( platform_name ... )
<- add_executable
   add_library()
   add_dependencies()
<- target_include_directories()
   target_compile_{definitions,features,options}
   target_link_{directories,libraries,options}
