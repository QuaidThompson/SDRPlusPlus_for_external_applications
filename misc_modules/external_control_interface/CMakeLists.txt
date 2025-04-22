# cmake_minimum_required(VERSION 3.13)
# project(rigctl_server)

# file(GLOB SRC "src/*.cpp")

# include(${SDRPP_MODULE_CMAKE})

# target_include_directories(rigctl_server PRIVATE "src/")
# target_include_directories(rigctl_server PRIVATE "../recorder/src")
# target_include_directories(rigctl_server PRIVATE "../../decoder_modules/meteor_demodulator/src")
# target_include_directories(rigctl_server PRIVATE "../../decoder_modules/radio/src")



cmake_minimum_required(VERSION 3.13)
project(external_control_interface)

# collect your sources
file(GLOB SRC "src/*.cpp")

# this sets up the shared‐lib + links to sdrpp_core
include(${SDRPP_MODULE_CMAKE})

# —— ADD THIS BLOCK —— 
target_include_directories(external_control_interface
  PRIVATE
    "src/"                                      # your module’s own headers
    "${SDRPP_CORE_ROOT}/src/"                  # SDR++ core headers
    "${CMAKE_SOURCE_DIR}/misc_modules/recorder/src/"  # for recorder_interface.h
)
# —— END ADDITION ——
