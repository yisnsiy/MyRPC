# set(SRC_LIST userservice.cc ../user.pb.cc)
set(SRC_LIST friendservice.cc ../friend.pb.cc)

add_executable(provider_friend ${SRC_LIST})

target_link_libraries(provider_friend mprpc protobuf)
