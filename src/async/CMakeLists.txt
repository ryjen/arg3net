
set(SOURCE_FILES client.cpp server.cpp)

set(${PROJECT_NAME_ASYNC}_HEADER_FILES
  client.h server.h
)

add_library(${PROJECT_NAME_ASYNC} ${SOURCE_FILES})

target_link_libraries(${PROJECT_NAME_ASYNC} INTERFACE ${PROJECT_NAME})

create_packages(TARGET ${PROJECT_NAME_ASYNC} DESCRIPTION "A c++ async server library.")

string(REPLACE "_" "/" INSTALL_DIRECTORY ${PROJECT_NAME_ASYNC})

install(FILES ${${PROJECT_NAME_ASYNC}_HEADER_FILES} DESTINATION "${CMAKE_INSTALL_PREFIX}/include/${INSTALL_DIRECTORY}")

install(TARGETS ${PROJECT_NAME_ASYNC} LIBRARY DESTINATION lib ARCHIVE DESTINATION lib)
