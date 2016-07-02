cmake_minimum_required (VERSION 2.8)

project ({{ cookiecutter.kata|lower }}-kata)

# We have gtest/gmock as a Git submoduile, add subdirectory to pick
# this up we we can use it as a dependency
add_subdirectory(lib/gtest)

# For the sake of form, and to give an idea of the sort of setup you'd
# find in a "real world" project, we're keeping the sources separate,
# and creating a separate archive
file (GLOB productionSources src/*.cpp)
add_library ({{ cookiecutter.kata|lower }} STATIC ${productionSources})
target_include_directories ({{ cookiecutter.kata|lower }} PRIVATE ${PROJECT_SOURCE_DIR}/include)

file (GLOB testSources test/*.cpp)
add_executable ({{ cookiecutter.kata|lower }}test ${testSources})
target_link_libraries ({{ cookiecutter.kata|lower }}test {{ cookiecutter.kata|lower }} gmock gmock_main gtest pthread)
target_include_directories ({{ cookiecutter.kata|lower }}test PRIVATE ${gtest_SOURCE_DIR}/include)
target_include_directories ({{ cookiecutter.kata|lower }}test PRIVATE ${gmock_SOURCE_DIR}/include)
target_include_directories ({{ cookiecutter.kata|lower }}test PRIVATE ${PROJECT_SOURCE_DIR}/include)

# This enables the "make test" target, although for TDD it's likely
# you'll want to use the "make unit" target.
enable_testing ()

# Add the unit tests executable 
add_test (Unit {{ cookiecutter.kata|lower }}test)

{% if cookiecutter.etags is equalto 'y' %}
# Generate the tags file
file (GLOB headers ${PROJECT_SOURCE_DIR}/include/*.hpp)
set_source_files_properties(TAGS PROPERTIES GENERATED true)
add_custom_command(OUTPUT TAGS
  COMMAND etags --language=c++ --declarations --ignore-indentation
  ${productionSources} ${testSources} ${headers}
  WORKING_DIRECTORY ${CMAKE_BINARY_DIR})
{% endif %}

# And a custom target as a convenience for running "make unit" as a
# specific target to support the TDD cycle
add_custom_target(unit
  COMMAND ${CMAKE_BINARY_DIR}/{{ cookiecutter.kata|lower }}test --gtest_color=true
  DEPENDS {{ cookiecutter.kata|lower }}test {% if cookiecutter.etags is equalto 'y' %} TAGS {% endif %})
