cmake_minimum_required(VERSION 3.13.4)

# Включаем модуль Geode (он скачает всё необходимое)
include(FetchContent)
FetchContent_Declare(
    Geode
    GIT_REPOSITORY https://github.com/geode-sdk/geode.git
    GIT_TAG main
)
FetchContent_MakeAvailable(Geode)

# Настройка вашего проекта мода
project(MyGeodeMod VERSION 1.0.0 LANGUAGES CXX)

# Регистрация мода в Geode
setup_geode_mod(${PROJECT_NAME})

# Автоматический поиск всех .cpp и .hpp файлов в папке src/
file(GLOB_RECURSE SOURCES CONFIGURE_DEPENDS "src/*.cpp" "src/*.hpp")

# Добавление исходных файлов в проект
target_sources(${PROJECT_NAME} PRIVATE ${SOURCES})
