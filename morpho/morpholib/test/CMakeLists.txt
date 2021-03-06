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

include_directories(${STRUTEXT_ROOT_SOURCE_DIR}/encode)
include_directories(${STRUTEXT_ROOT_SOURCE_DIR}/symbols)
include_directories(${STRUTEXT_ROOT_SOURCE_DIR}/automata)
include_directories(${STRUTEXT_ROOT_SOURCE_DIR}/morpho/models)
include_directories(${STRUTEXT_ROOT_SOURCE_DIR}/morpho/alphabets)
include_directories(${STRUTEXT_ROOT_SOURCE_DIR}/morpho/morpholib)

set(UNIT_TEST_NAME morpholib-unit-test)
set(UNIT_TEST_SOURCES
  ${STRUTEXT_ROOT_SOURCE_DIR}/ut-data/ut_main.cpp
  test.cpp
)

add_executable(${UNIT_TEST_NAME} ${UNIT_TEST_SOURCES})
target_link_libraries(${UNIT_TEST_NAME}
  morpho
  ${Boost_UNIT_TEST_FRAMEWORK_LIBRARY}
  ${Log4cplus_LIBRARY}
  ${Boost_REGEX_LIBRARY}
  ${Boost_SYSTEM_LIBRARY}
)

add_boost_tests("${CMAKE_RUNTIME_OUTPUT_DIRECTORY}/${UNIT_TEST_NAME}" "--catch_system_errors=no" ${UNIT_TEST_SOURCES})
