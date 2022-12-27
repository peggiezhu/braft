licenses(["notice"])

load("@com_github_brpc_braft//:bazel/braft.bzl", "braft_proto_library")

cc_binary(
    name = "atomic_client",
    srcs = [
        "client.cpp"
    ],
    linkopts = [
        "-ldl",
    ],
    deps = [
        "@com_github_brpc_braft//:braft",
        ":braft_automic_proto"
    ],
    copts = [
        "-DGFLAGS_NS=google",
    ],
    linkstatic = 1,
    visibility = ["//visibility:public"],
)

cc_binary(
    name = "atomic_server",
    srcs = [
        "server.cpp"
    ],
    linkopts = [
        "-ldl",
    ],
    copts = [
        "-DGFLAGS_NS=google",
    ],
    deps = [
        "@com_github_brpc_braft//:braft",
        ":braft_automic_proto"
    ],
    visibility = ["//visibility:public"],
)

braft_proto_library(
    name = "braft_automic_proto",
    srcs = ["atomic.proto"],
    visibility = ["//visibility:public"],
)