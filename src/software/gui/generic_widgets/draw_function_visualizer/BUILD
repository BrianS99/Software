load("@bazel_rules_qt//:qt.bzl", "qt_cc_library")

package(default_visibility = ["//software/gui:__subpackages__"])

qt_cc_library(
    name = "draw_function_visualizer",
    src = "draw_function_visualizer.cpp",
    hdr = "draw_function_visualizer.h",
    deps = [
        ":zoomable_qgraphics_view",
        "//software/geom:rectangle",
        "//software/gui:geometry_conversion",
        "//software/gui/drawing:colors",
        "//software/gui/drawing:draw_functions",
        "//software/logger",
        "@qt//:qt_core",
        "@qt//:qt_widgets",
    ],
)

qt_cc_library(
    name = "zoomable_qgraphics_view",
    src = "zoomable_qgraphics_view.cpp",
    hdr = "zoomable_qgraphics_view.h",
    deps = [
        "@qt//:qt_gui",
        "@qt//:qt_widgets",
    ],
)
