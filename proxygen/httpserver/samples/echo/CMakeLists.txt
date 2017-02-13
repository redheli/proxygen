# This code is released under the
# Apache License Version 2.0 http://www.apache.org/licenses/.
#
# Copyright (c) 2012 Louis Dionne
#
cmake_minimum_required(VERSION 2.8.7)

project(PROXYGEN-ECHO CXX C)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++14 -Wall -Wextra")

include_directories(/usr/local/include/proxygen/)
link_directories(/user/local/lib)
link_directories(/usr/lib/x86_64-linux-gnu/)

set(SRC EchoServer.cpp
	EchoHandler.cpp
)

add_executable(echo-server ${SRC})
target_link_libraries(echo-server 	proxygenhttpserver 
					folly
					glog
					gflags
					pthread
)
