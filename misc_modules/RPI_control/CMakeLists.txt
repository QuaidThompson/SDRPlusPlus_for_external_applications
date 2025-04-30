


cmake_minimum_required(VERSION 3.13)
project(RPI_control)


file(GLOB SRC "src/*.cpp")


include(${SDRPP_MODULE_CMAKE})


target_include_directories(external_control_interface
  PRIVATE
    "src/"
    "${SDRPP_CORE_ROOT}/src/"
    "${CMAKE_SOURCE_DIR}/misc_modules/recorder/src/"
    "${CMAKE_SOURCE_DIR}/decoder_modules/meteor_demodulator/src/"
    "${CMAKE_SOURCE_DIR}/decoder_modules/radio/src/"
)
