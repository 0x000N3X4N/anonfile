cmake_minimum_required(VERSION 3.9)
project(anonfile)

set(CMAKE_CXX_STANDARD 20)
set(CURL_LIBRARY "-lcurl")
find_package(CURL REQUIRED)
find_package(OpenSSL REQUIRED)


add_executable(anonfile main.cpp helpers/helpers.cpp helpers/helpers.h pjson/pjson.h json_handler/JHandler.cpp json_handler/JHandler.h sendReceiver/sendReceiver.cpp sendReceiver/sendReceiver.h)

include_directories(${CURL_INCLUDE_DIR})
target_link_libraries(anonfile ${CURL_LIBRARIES})
target_link_libraries(anonfile OpenSSL::SSL)
