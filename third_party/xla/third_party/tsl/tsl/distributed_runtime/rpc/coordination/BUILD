load("@local_tsl//tsl/platform:rules_cc.bzl", "cc_library")
load("@local_xla//xla/tsl:tsl.bzl", "internal_visibility")
load("@local_xla//xla/tsl:tsl.default.bzl", "tsl_grpc_cc_dependencies")

package(
    # copybara:uncomment default_applicable_licenses = ["//tensorflow:license"],
    default_visibility = internal_visibility([
        "@local_xla//xla/tsl:internal",
    ]),
    licenses = ["notice"],
)

cc_library(
    name = "grpc_coordination_client",
    srcs = ["grpc_coordination_client.cc"],
    hdrs = ["grpc_coordination_client.h"],
    deps = [
        "//tsl/distributed_runtime:call_options",
        "//tsl/distributed_runtime/coordination:coordination_client",
        "//tsl/distributed_runtime/rpc:grpc_channel",
        "//tsl/distributed_runtime/rpc:grpc_client_cq_tag",
        "//tsl/distributed_runtime/rpc:grpc_state",
        "//tsl/distributed_runtime/rpc:grpc_util",
        "//tsl/platform:mutex",
        "//tsl/platform:protobuf",
        "//tsl/platform:status",
        "//tsl/platform:thread_annotations",
        "//tsl/protobuf:coordination_service_proto_cc",
    ],
)

cc_library(
    name = "grpc_coordination_service_impl",
    srcs = ["grpc_coordination_service_impl.cc"],
    hdrs = ["grpc_coordination_service_impl.h"],
    deps = [
        "//tsl/distributed_runtime/coordination:coordination_service_agent",
        "//tsl/distributed_runtime/coordination:coordination_service_rpc_handler",
        "//tsl/distributed_runtime/rpc:async_service_interface",
        "//tsl/distributed_runtime/rpc:grpc_call",
        "//tsl/distributed_runtime/rpc:grpc_util",
        "//tsl/platform:env",
        "//tsl/platform:mutex",
        "//tsl/platform:thread_annotations",
        "//tsl/protobuf:coordination_service_cc_grpc_proto",
        "//tsl/protobuf:coordination_service_proto_cc",
    ] + tsl_grpc_cc_dependencies(),
)
