#
# This file is part of MyCMakeTemplate.
#
# MyCMakeTemplate is free software: you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation, either version 3 of the License, or
# (at your option) any later version.
#
# MyCMakeTemplate is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with MyCMakeTemplate.  If not, see <https://www.gnu.org/licenses/>.
#

# Testing library
FetchContent_Declare(
    catch
    GIT_REPOSITORY https://github.com/catchorg/Catch2.git
    GIT_TAG v3.5.0)
FetchContent_MakeAvailable(catch)
list(APPEND CMAKE_MODULE_PATH ${catch2_SOURCE_DIR}/extras)
include(Catch)
# Adds Catch2::Catch2

# Tests need to be added as executables first
add_executable(test-main main.cpp)

# I'm using C++17 in the test
target_compile_features(test-main PRIVATE cxx_std_17)

# Should be linked to the main library, as well as the Catch2 testing library
target_link_libraries(test-main PRIVATE ${MY_CMAKE_TEMPLATE_LIB_NAME} Catch2::Catch2WithMain)

# Include directories
target_include_directories(test-main PRIVATE ${PROJECT_INCLUDE_DIR} ${PROJECT_GENERATED_INCLUDE_DIR} ${catch2_INCLUDE_DIRS})

# If you register a test, then ctest and make test will run it.
# You can also run examples and check the output, as well.
add_test(NAME testlibtest COMMAND test-main) # Command can be a target

catch_discover_tests(test-main)
