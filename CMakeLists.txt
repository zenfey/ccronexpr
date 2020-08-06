cmake_minimum_required(VERSION 3.0)


project(CCronExpr)

# Target.
add_library(ccronexpr_static STATIC include/ccronexpr.h src/ccronexpr.c)
target_include_directories(ccronexpr_static PUBLIC
  $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/include>
  $<INSTALL_INTERFACE:include>)
target_compile_features(ccronexpr_static PRIVATE cxx_std_17)
target_compile_options(ccronexpr_static PRIVATE -Wextra -Wall)
target_compile_definitions(ccronexpr_static PRIVATE -DCRON_USE_LOCAL_TIME)

