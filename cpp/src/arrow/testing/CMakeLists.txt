# Licensed to the Apache Software Foundation (ASF) under one
# or more contributor license agreements.  See the NOTICE file
# distributed with this work for additional information
# regarding copyright ownership.  The ASF licenses this file
# to you under the Apache License, Version 2.0 (the
# "License"); you may not use this file except in compliance
# with the License.  You may obtain a copy of the License at
#
#   http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing,
# software distributed under the License is distributed on an
# "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
# KIND, either express or implied.  See the License for the
# specific language governing permissions and limitations
# under the License.

arrow_install_all_headers("arrow/testing")

if(ARROW_BUILD_TESTS)
  add_arrow_test(generator_test)
  add_arrow_test(gtest_util_test)
  add_arrow_test(random_test)

  if(ARROW_FILESYSTEM)
    add_library(arrow_filesystem_example MODULE examplefs.cc)
    target_link_libraries(arrow_filesystem_example ${ARROW_TEST_LINK_LIBS}
                          ${ARROW_EXAMPLE_LINK_LIBS})
  endif()
endif()
