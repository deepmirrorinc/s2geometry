cc_library(
    name = "base",
    srcs = glob([
        "s2/base/*.cc",
    ]),
    hdrs = glob([
        "s2/base/*.h",
    ]),
    defines = [
        "S2_USE_GLOG",
        "S2_USE_GFLAGS",
    ],
    includes = ["."],
    visibility = ["//visibility:public"],
    deps = [
        "@com_github_glog//:glog",
    ],
)

cc_library(
    name = "strings",
    srcs = glob([
        "s2/strings/*.cc",
    ]),
    hdrs = glob([
        "s2/strings/*.h",
    ]),
    includes = ["."],
    visibility = ["//visibility:public"],
    deps = [
        ":base",
    ],
)

cc_library(
    name = "util",
    srcs = glob([
        "s2/util/**/*.cc",
    ]),
    hdrs = glob([
        "s2/util/**/*.h",
    ]),
    defines = [
        "OPENSSL_IS_BORINGSSL",
    ],
    includes = ["."],
    visibility = ["//visibility:public"],
    deps = [
        ":base",
        ":strings",
        "@boringssl//:ssl",
    ],
)

cc_library(
    name = "s2geometry",
    srcs = glob(
        [
            "s2/*.cc",
        ],
        exclude = [
            "s2/*_test.cc",
            "s2/*_testing.cc",
        ],
    ),
    hdrs = glob(
        [
            "s2/*.h",
        ],
        exclude = [
            "s2/*_testing.h",
        ],
    ),
    includes = ["."],
    visibility = ["//visibility:public"],
    deps = [
        ":base",
        ":strings",
        ":util",
    ],
)
