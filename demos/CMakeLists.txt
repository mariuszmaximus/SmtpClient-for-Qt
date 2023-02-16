

aux_source_directory(./demo1 SRC_FILES_DEMO1)
add_executable(demo1 ${SRC_FILES_DEMO1})
target_link_libraries(demo1 SMTPEmail)