cmake_minimum_required(VERSION 2.8.12)

project(RustIntroSlides NONE)

include(${CMAKE_CURRENT_LIST_DIR}/deps/UseLATEX/UseLATEX.cmake)

set(PDFLATEX_COMPILER lualatex)

add_latex_document(
  slides.tex INPUTS defs.tex frames/01-basic-information/02-principles.tex
  frames/01-basic-information/03-target-domains.tex)
