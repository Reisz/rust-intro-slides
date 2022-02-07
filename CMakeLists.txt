cmake_minimum_required(VERSION 2.8.12)

project(RustIntroSlides NONE)

# Imports
include(${CMAKE_CURRENT_LIST_DIR}/deps/UseLATEX/UseLATEX.cmake)

# Config
set(PDFLATEX_COMPILER lualatex)

# Frames
set(SECTIONS "01-basic-information" "02-language-intro")
set(FRAMES_01-basic-information "02-principles" "03-target-domains")
set(FRAMES_02-language-intro "01-integer-types")

# Inputs
set(INPUTS defs.tex)
foreach(SECTION IN LISTS SECTIONS)
    foreach(FRAME IN LISTS FRAMES_${SECTION})
        list(APPEND INPUTS frames/${SECTION}/${FRAME}.tex)
    endforeach()
endforeach()

# Targets
add_latex_document(slides.tex INPUTS ${INPUTS})
