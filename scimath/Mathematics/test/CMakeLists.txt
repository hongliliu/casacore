set (tests
dAutoDiff
dSparseDiff
tAutoDiff
tChauvenetCriterionStatistics
tClassicalStatistics
tCombinatorics
tConvolver
tFFTServer
tFFTServer2
tFitToHalfStatistics
tGaussianBeam
tGeometry
tHingesFencesStatistics
tHistAcc
tInterpolateArray1D
tMathFunc
tMatrixMathLA
tMedianSlider
tSmooth
tSparseDiff
tStatAcc
tStatisticsTypes
tStatisticsUtilities
tVanVleck
tVectorKernel
tZScoreCalculator
tInterpolate2D
)

foreach (test ${tests})
    add_executable (${test} ${test}.cc)
    target_link_libraries (${test} casa_scimath)
    add_test (${test} ${CMAKE_SOURCE_DIR}/cmake/cmake_assay ./${test})
    add_dependencies(check ${test})
endforeach (test)
