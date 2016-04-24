cmake_minimum_required(VERSION 2.8.3)
project(genjs)
find_package(catkin REQUIRED COMPONENTS genmsg)

catkin_package(
  CATKIN_DEPENDS genmsg
  CFG_EXTRAS genjs-extras.cmake
)

add_subdirectory(scripts)

file(WRITE ${CATKIN_DEVEL_PREFIX}/${GENMSG_LANGS_DESTINATION}/genjs "JAVASCRIPT")
install(FILES ${CATKIN_DEVEL_PREFIX}/${GENMSG_LANGS_DESTINATION}/genjs
  DESTINATION ${GENMSG_LANGS_DESTINATION})

# install base serialization, deserialization files
set(base_files
  src/genjs/base_serialize.js
  src/genjs/base_deserialize.js
  src/genjs/find.js)

file(COPY ${base_files} DESTINATION ${CATKIN_DEVEL_PREFIX}/share/node_js)
install(FILES ${base_files}
  DESTINATION ${CATKIN_GLOBAL_SHARE_DESTINATION}/node_js)

# drop marker file to prevent rospack from spending time on crawling this folder
#file(WRITE ${CATKIN_DEVEL_PREFIX}/share/nodejs/rospack_nosubdirs "")
#install(FILES ${CATKIN_DEVEL_PREFIX}/share/nodejs/rospack_nosubdirs
#  DESTINATION share/nodejs)

catkin_python_setup()
