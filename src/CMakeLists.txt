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

set(MY_CMAKE_TEMPLATE_LIB_NAME my-cmake-template CACHE INTERNAL "")


# Make an automatic library - will be static or dynamic based on user setting
add_library(${MY_CMAKE_TEMPLATE_LIB_NAME} ./lib.cpp ${PROJECT_HEADER_FILES} ${PROJECT_GENERATED_HEADER_FILES})

# We need this directory, and users of our library will need it too
target_include_directories(${MY_CMAKE_TEMPLATE_LIB_NAME} PUBLIC ${PROJECT_INCLUDE_DIR} ${PROJECT_GENERATED_INCLUDE_DIR})

# All users of this library will need at least C++11
target_compile_features(${MY_CMAKE_TEMPLATE_LIB_NAME} PUBLIC cxx_std_11)

# IDEs should put the headers in a nice place
source_group(
    TREE "${PROJECT_INCLUDE_DIR}"
    PREFIX "Header Files"
    FILES ${PROJECT_HEADER_FILES})
source_group(
    TREE "${PROJECT_GENERATED_INCLUDE_DIR}"
    PREFIX "Generated Header Files"
    FILES ${PROJECT_GENERATED_HEADER_FILES})

if(IS_IPO_SUPPORTED)
  set_target_properties(${MY_CMAKE_TEMPLATE_LIB_NAME} PROPERTIES INTERPROCEDURAL_OPTIMIZATION TRUE)
endif()
