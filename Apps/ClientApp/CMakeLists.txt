add_executable(ClientApp
        src/ClientApp/main.cpp
)

target_include_directories(ClientApp PRIVATE include)

target_link_libraries(ClientApp PRIVATE
        ProjectWarnings
)