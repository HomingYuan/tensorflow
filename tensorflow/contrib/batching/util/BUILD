# Description: Utilities.

package(
    default_visibility = ["//tensorflow:internal"],
    features = ["-layering_check"],
)

licenses(["notice"])  # Apache 2.0

exports_files(["LICENSE"])

filegroup(
    name = "all_files",
    srcs = glob(
        ["**/*"],
        exclude = [
            "**/METADATA",
            "**/OWNERS",
            "**/google_*",
        ],
    ),
)

cc_library(
    name = "periodic_function_dynamic",
    srcs = ["periodic_function.cc"],
    hdrs = ["periodic_function.h"],
    visibility = ["//visibility:public"],
    deps = [
        "//tensorflow/core:framework_headers_lib",
        "//tensorflow/core:protos_all_cc",
    ],
)

cc_library(
    name = "periodic_function",
    visibility = ["//visibility:public"],
    deps = [
        ":periodic_function_dynamic",
        "//tensorflow/core:lib",
    ],
)

cc_test(
    name = "periodic_function_test",
    srcs = ["periodic_function_test.cc"],
    deps = [
        ":periodic_function",
        "//tensorflow/contrib/batching/test_util:fake_clock_env",
        "//tensorflow/core:test_main",
    ],
)
