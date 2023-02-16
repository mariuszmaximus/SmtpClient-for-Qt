




#make sure MOC compiler is called in parallel
set(CMAKE_AUTOGEN_PARALLEL AUTO)

# Find includes in corresponding build directories
set(CMAKE_INCLUDE_CURRENT_DIR ON)

# Instruct CMake to run moc automatically when needed.
set(CMAKE_AUTOMOC ON)

# Instruct CMake to create code from Qt resource files (*.qrc)
set(CMAKE_AUTORCC ON)

# UI ==> H generator from QT   # Instruct CMake to create code from Qt designer ui files
set(CMAKE_AUTOUIC ON)

# Find the QtWidgets library
find_package(${QT_VERSION_BASE} COMPONENTS Core Gui Widgets Network REQUIRED)


aux_source_directory(. SRC_FILES)
add_library(SMTPEmail SHARED ${SRC_FILES})

target_link_libraries(SMTPEmail PUBLIC ${QT_VERSION_BASE}::Core  ${QT_VERSION_BASE}::Widgets ${QT_VERSION_BASE}::Network )




if(FIX_BY_MAXIMUS)
    target_compile_definitions(SMTPEmail PRIVATE FIX_BY_MAXIMUS)
else()
    target_compile_definitions(SMTPEmail PRIVATE SMTP_MIME_LIBRARY)
endif(FIX_BY_MAXIMUS)
