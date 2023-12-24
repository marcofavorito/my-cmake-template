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

set(DOXYGEN_EXTRACT_ALL YES)
set(DOXYGEN_BUILTIN_STL_SUPPORT YES)

doxygen_add_docs(docs modern/lib.hpp "${CMAKE_CURRENT_SOURCE_DIR}/main.md"
    WORKING_DIRECTORY "${PROJECT_SOURCE_DIR}/include")
