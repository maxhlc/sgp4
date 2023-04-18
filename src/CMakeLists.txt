# Collect all source files
file(GLOB_RECURSE ${PROJECT_NAME}_cpp CONFIGURE_DEPENDS ${CMAKE_CURRENT_SOURCE_DIR}/*.cpp)

# Collect all header files
file(GLOB_RECURSE ${PROJECT_NAME}_hpp CONFIGURE_DEPENDS ${PROJECT_SOURCE_DIR}/include/*.hpp)

# Build library
add_library(${PROJECT_NAME} "${${PROJECT_NAME}_cpp}" "${${PROJECT_NAME}_hpp}")

# Set target properties
set_target_properties(${PROJECT_NAME} PROPERTIES POSITION_INDEPENDENT_CODE ON)
set_target_properties(${PROJECT_NAME} PROPERTIES PUBLIC_HEADER "${PROJECT_NAME}_hpp")

# Include header directory
target_include_directories(${PROJECT_NAME} PUBLIC ${PROJECT_SOURCE_DIR}/include)