if(NOT VTK_SOURCE_DIR)
  cmake_minimum_required(VERSION 3.3 FATAL_ERROR)
  project(PoissonReconstruction)
  find_package(VTK REQUIRED)
endif()
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${VTK_CMAKE_DIR}")
if(NOT VTK_SOURCE_DIR)
  include(vtkExternalModuleMacros)
endif()

set(Module_SRCS
  vtkOneSheetedHyperboloidSource.cxx
  vtkTwoSheetedHyperboloidSource.cxx
  vtkSignedEigenvalueTensorGlyph.cxx
  )

vtk_module_library(SignedTensor ${Module_SRCS})
