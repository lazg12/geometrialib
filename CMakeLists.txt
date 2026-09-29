# ==============================================================================
# @file       CMakeLists.txt
# @brief      Configuración de compilación cross-platform para geometrialib
# @author     Luis Zambrano Gahón (ignot)
# @version    v1.0.0
# @date       28 de septiembre de 2026
# @copyright  MIT License
# ==============================================================================

cmake_minimum_required(VERSION 3.16)

# Declaración del proyecto C++20
project(
    geometrialib
    VERSION 1.0.0
    DESCRIPTION "Motor de Geometría Modular 1D/2D en C++20"
    LANGUAGES CXX
)

# Estándar C++20 estricto
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# Inclusión de directorio de encabezados públicos (.hpp)
include_directories(include)

# Configuración de Flags de Compilación Estricta (Clean Code & Zero Warnings)
if(MSVC)
    # Flags para el compilador de Microsoft Visual C++
    add_compile_options(/W4 /WX) # Nivel de advertencia 4 y tratar advertencias como errores
else()
    # Flags para GCC / Clang (Linux, MinGW)
    add_compile_options(-Wall -Wextra -Wpedantic -Werror)
endif()

# Mensaje informativo durante la generación
message(STATUS "--------------------------------------------------------")
message(STATUS " Proyecto : ${PROJECT_NAME} v${PROJECT_VERSION}")
message(STATUS " C++ Std  : C++${CMAKE_CXX_STANDARD}")
message(STATUS " Sistema  : ${CMAKE_SYSTEM_NAME}")
message(STATUS "--------------------------------------------------------")