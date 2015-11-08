PROJECT(presentation NONE)
cmake_minimum_required(VERSION 2.8)
SET(LATEX_OUTPUT_PATH build)
INCLUDE(../CMakeLatex/UseLATEX.cmake)

file(GLOB_RECURSE contents_files RELATIVE ${CMAKE_SOURCE_DIR} contents/*.tex)

ADD_LATEX_DOCUMENT(
    pres.tex
#    INPUTS ${contents_files}
    IMAGE_DIRS img 
#    BIBFILES pres.bib
#    USE_INDEX
#    USE_GLOSSARY
#    FILTER_OUTPUT
    )


