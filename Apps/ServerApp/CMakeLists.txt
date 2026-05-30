add_executable(ServerApp
        src/ServerApp/main.cpp
)

target_include_directories(ServerApp PRIVATE include)

target_link_libraries(ServerApp PRIVATE
        ProjectWarnings
)