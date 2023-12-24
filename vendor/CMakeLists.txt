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

# CMake build : third party

#configure directories
set (VENDOR_MODULE_PATH "${PROJECT_SOURCE_DIR}/vendor")

# -------------------------------------------------------------------------
# Formatting library
FetchContent_Declare(
    fmtlib
    GIT_REPOSITORY https://github.com/fmtlib/fmt.git
    GIT_TAG 5.3.0)
FetchContent_MakeAvailable(fmtlib)
# -------------------------------------------------------------------------
# -------------------------------------------------------------------------
# Logging library
FetchContent_Declare(
    spdloglib
    GIT_REPOSITORY https://github.com/gabime/spdlog
    GIT_TAG v1.12.0)
FetchContent_MakeAvailable(spdloglib)
# -------------------------------------------------------------------------
# -------------------------------------------------------------------------
