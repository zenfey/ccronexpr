cmake_minimum_required(VERSION 3.0)


project(CCronExpr)

# Target.
add_library(ccronexpr_static STATIC ccronexpr.h ccronexpr.c)
target_compile_features(ccronexpr_static PRIVATE cxx_std_17)
target_compile_options(ccronexpr_static PRIVATE -Wextra -Wall)

add_executable(ccronexpr_test ccronexpr_test.c)
target_compile_options(ccronexpr_test PRIVATE -Wall -Wextra)
target_compile_features(ccronexpr_test PRIVATE cxx_std_17)
target_compile_definitions(ccronexpr_test PRIVATE CRON_TEST_MALLOC)
target_link_libraries(ccronexpr_test PRIVATE
  ccronexpr_static
)

