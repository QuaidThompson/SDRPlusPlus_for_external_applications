# cmake_minimum_required(VERSION 3.13)
# project(rigctl_server)

# file(GLOB SRC "src/*.cpp")

# include(${SDRPP_MODULE_CMAKE})




cmake_minimum_required(VERSION 3.13)
project(external_control_interface)

file(GLOB SRC "src/*.cpp")


include(${SDRPP_MODULE_CMAKE})


target_include_directories(external_control_interface
PRIVATE
"src/"
"${SDRPP_CORE_ROOT}/src/"
"${CMAKE_SOURCE_DIR}/misc_modules/recorder/src/"
)
target_include_directories(rigctl_server PRIVATE "src/")
target_include_directories(rigctl_server PRIVATE "../recorder/src")
target_include_directories(rigctl_server PRIVATE "../../decoder_modules/meteor_demodulator/src")
target_include_directories(rigctl_server PRIVATE "../../decoder_modules/radio/src")
