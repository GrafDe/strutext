# Copyright &copy; 2013, Vladimir Lapshin.
#
#   Licensed under the Apache License, Version 2.0 (the "License");
#   you may not use this file except in compliance with the License.
#   You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
#   Unless required by applicable law or agreed to in writing, software
#   distributed under the License is distributed on an "AS IS" BASIS,
#   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
#   See the License for the specific language governing permissions and
#   limitations under the License.

include_directories(${CMAKE_CURRENT_SOURCE_DIR})
include_directories(${STRUTEXT_ROOT_SOURCE_DIR}/encode)
include_directories(${STRUTEXT_ROOT_SOURCE_DIR}/automata)
include_directories(${STRUTEXT_ROOT_SOURCE_DIR}/symbols)
include_directories(${STRUTEXT_ROOT_SOURCE_DIR}/morpho/alphabets)

# morpho library.
set(NAME morpho)
add_library(${NAME} STATIC
  morpho.cpp
  suffix_storage.cpp
  base_storage.cpp
)

target_link_libraries(${NAME}
  symbols
  encode
  automata
  ${Boost_SERIALIZATION_LIBRARY}
)

add_subdirectory(test)
