
set(test_list
  queue.c
  csr_matrix.c
  csr_matrix_io.c
  csr_matrix_permute.c
  mesh.c
  )

foreach(test ${test_list})
  string(REPLACE ".c" "" test ${test})
  add_executable(${test} ${rcm_SOURCE_DIR}/test/${test}.c)
  target_link_libraries(${test} rcm m)
  add_test(${test} ${test})
endforeach(test)
