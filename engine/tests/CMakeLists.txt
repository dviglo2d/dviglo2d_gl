# В IDE таргеты будут отображаться в папке "тесты"
set(CMAKE_FOLDER тесты)

# Указываем папку для следующих скомпилированных экзешников
dv_set_bin_dir(${CMAKE_BINARY_DIR}/result)

# Копируем ресурсы в result
execute_process(COMMAND ${CMAKE_COMMAND} -E copy_directory_if_newer
                    ${CMAKE_CURRENT_SOURCE_DIR}/../result/engine_data
                    ${dv_bin_dir}/engine_data)

execute_process(COMMAND ${CMAKE_COMMAND} -E copy_directory_if_newer
                    ${CMAKE_CURRENT_SOURCE_DIR}/../result/engine_test_data
                    ${dv_bin_dir}/engine_test_data)

add_subdirectory(benchmark)
add_subdirectory(hello)
add_subdirectory(tester)
