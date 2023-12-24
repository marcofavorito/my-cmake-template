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

set(MY_CMAKE_TEMPLATE_APP_NAME my-cmake-template-app CACHE INTERNAL "")

add_executable(${MY_CMAKE_TEMPLATE_APP_NAME} main.cpp)
target_compile_features(${MY_CMAKE_TEMPLATE_APP_NAME} PRIVATE cxx_std_17)

target_link_libraries(${MY_CMAKE_TEMPLATE_APP_NAME} PRIVATE ${MY_CMAKE_TEMPLATE_LIB_NAME} fmt::fmt)
target_include_directories(${MY_CMAKE_TEMPLATE_APP_NAME} PUBLIC ${PROJECT_INCLUDE_DIR} ${PROJECT_GENERATED_INCLUDE_DIR})
