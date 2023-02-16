
aux_source_directory(. SRC_FILES)
add_executable(test ${SRC_FILES})

target_link_libraries(test SMTPEmail)