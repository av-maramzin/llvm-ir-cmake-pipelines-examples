# cmake file

set(EXAMPLE_NAME "foo")

add_executable(${EXAMPLE_NAME}
  ${EXAMPLE_NAME}.cpp)

set_target_properties(${EXAMPLE_NAME} PROPERTIES LINKER_LANGUAGE CXX)

if(COMMAND loopc14n_full)
  loopc14n_full(DEPENDS ${EXAMPLE_NAME}
    MAIN_TARGET PLINE_TRGT1
    TARGET_LIST PLINE_TRGTS)

  message(STATUS "loopc14n_full pipeline main target: ${PLINE_TRGT1}")
  message(STATUS "loopc14n_full pipeline intermediate targets: ${PLINE_TRGTS}")
endif()

# installation

