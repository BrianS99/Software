package(default_visibility = ["//visibility:public"])

cc_library(
    name = "ball",
    srcs = ["ball.cpp"],
    hdrs = ["ball.h"],
    deps = [
        "//shared:constants",
        "//software/geom:point",
        "//software/geom:vector",
        "//software/time:timestamp",
        "//software/world:timestamped_ball_state",
        "//software/world/ball_model",
        "//software/world/ball_model:two_stage_linear_ball_model",
    ],
)

cc_test(
    name = "ball_test",
    srcs = ["ball_test.cpp"],
    deps = [
        ":ball",
        ":timestamped_ball_state",
        "@gtest//:gtest_main",
    ],
)

cc_library(
    name = "timestamped_ball_state",
    srcs = ["timestamped_ball_state.cpp"],
    hdrs = ["timestamped_ball_state.h"],
    deps = [
        ":ball_state",
        "//software/geom:point",
        "//software/geom:vector",
        "//software/time:timestamp",
        "@boost//:circular_buffer",
    ],
)

cc_test(
    name = "timestamped_ball_state_test",
    srcs = ["timestamped_ball_state_test.cpp"],
    deps = [
        ":timestamped_ball_state",
        "@gtest//:gtest_main",
    ],
)

cc_library(
    name = "ball_state",
    srcs = ["ball_state.cpp"],
    hdrs = ["ball_state.h"],
    deps = [
        "//software/geom:point",
        "//software/geom:vector",
    ],
)

cc_test(
    name = "ball_state_test",
    srcs = ["ball_state_test.cpp"],
    deps = [
        ":ball_state",
        "@gtest//:gtest_main",
    ],
)

cc_library(
    name = "field",
    srcs = ["field.cpp"],
    hdrs = ["field.h"],
    deps = [
        "//shared:constants",
        "//software/geom:circle",
        "//software/geom:rectangle",
        "//software/geom/algorithms",
        "//software/time:timestamp",
    ],
)

cc_test(
    name = "field_test",
    srcs = ["field_test.cpp"],
    deps = [
        ":field",
        "//shared:constants",
        "@gtest//:gtest_main",
    ],
)

cc_library(
    name = "game_state",
    srcs = ["game_state.cpp"],
    hdrs = ["game_state.h"],
    deps = [
        ":ball",
        "//software/logger",
        "//software/util/make_enum",
    ],
)

cc_test(
    name = "game_state_test",
    srcs = ["game_state_test.cpp"],
    deps = [
        ":game_state",
        "//software/test_util",
        "@gtest//:gtest_main",
    ],
)

cc_library(
    name = "team_colour",
    hdrs = ["team_colour.h"],
    deps = ["//software/util/make_enum"],
)

cc_library(
    name = "robot",
    srcs = ["robot.cpp"],
    hdrs = ["robot.h"],
    deps = [
        ":robot_capabilities",
        ":timestamped_robot_state",
        "//software/logger",
        "//software/time:duration",
        "//software/time:timestamp",
    ],
)

cc_test(
    name = "robot_test",
    srcs = ["robot_test.cpp"],
    deps = [
        ":robot",
        "@gtest//:gtest_main",
    ],
)

cc_library(
    name = "timestamped_robot_state",
    srcs = ["timestamped_robot_state.cpp"],
    hdrs = ["timestamped_robot_state.h"],
    deps = [
        ":robot_state",
        "//software/geom:angle",
        "//software/geom:angular_velocity",
        "//software/geom:point",
        "//software/geom:vector",
        "//software/time:timestamp",
        "@boost//:circular_buffer",
    ],
)

cc_test(
    name = "timestamped_robot_state_test",
    srcs = ["timestamped_robot_state_test.cpp"],
    deps = [
        ":timestamped_robot_state",
        "@gtest//:gtest_main",
    ],
)

cc_library(
    name = "robot_state",
    srcs = ["robot_state.cpp"],
    hdrs = ["robot_state.h"],
    deps = [
        "team_colour",
        "//shared:constants",
        "//software/geom:angle",
        "//software/geom:angular_velocity",
        "//software/geom:point",
        "//software/geom:vector",
        "//software/time:duration",
    ],
)

cc_test(
    name = "robot_state_test",
    srcs = ["robot_state_test.cpp"],
    deps = [
        ":robot_state",
        "@gtest//:gtest_main",
    ],
)

cc_library(
    name = "robot_capabilities",
    hdrs = ["robot_capabilities.h"],
    deps = ["//software/util/make_enum"],
)

cc_test(
    name = "robot_capabilities_test",
    srcs = ["robot_capabilities_test.cpp"],
    deps = [
        "robot_capabilities",
        "@gtest//:gtest_main",
    ],
)

cc_library(
    name = "team",
    srcs = ["team.cpp"],
    hdrs = ["team.h"],
    deps = [
        ":robot",
        "//software/logger",
    ],
)

cc_test(
    name = "team_test",
    srcs = ["team_test.cpp"],
    deps = [
        ":team",
        "@gtest//:gtest_main",
    ],
)

cc_library(
    name = "world",
    srcs = ["world.cpp"],
    hdrs = ["world.h"],
    deps = [
        ":ball",
        ":field",
        ":game_state",
        ":robot",
        ":team",
        "//software/parameter:dynamic_parameters",
    ],
)

cc_test(
    name = "world_test",
    srcs = ["world_test.cpp"],
    deps = [
        ":world",
        "//software/test_util",
        "@gtest//:gtest_main",
    ],
)
