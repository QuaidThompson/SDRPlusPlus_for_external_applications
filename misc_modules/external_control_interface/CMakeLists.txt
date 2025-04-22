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

# collect all your .cpp/.c files
file(GLOB SRC "src/*.cpp" "src/*.c")

# this includes the helper that turns SRC into a plugin linked against core
include(${SDRPP_MODULE_CMAKE})

# if you need to include SDR++ headers, you can also add:
target_include_directories(external_control_interface
  PRIVATE
    "src/"
    "${SDRPP_CORE_ROOT}/src/"
)
