licenses(["notice"])  # Apache 2

load(
    "//bazel:envoy_build_system.bzl",
    "envoy_package",
    "envoy_proto_library",
    "envoy_proto_descriptor",
)

envoy_package()

exports_files(["bookstore.proto"])

envoy_proto_library(
    name = "helloworld_proto",
    srcs = [":helloworld.proto"],
)

envoy_proto_library(
    name = "bookstore_proto",
    srcs = [":bookstore.proto"],
    external_deps = [
        "http_api_protos",
        "cc_wkt_protos",
    ],
)

envoy_proto_descriptor(
    name = "bookstore_proto_descriptor",
    srcs = [
        "bookstore.proto",
    ],
    out = "bookstore.descriptor",
    external_deps = [
        "http_api_protos",
        "well_known_protos",
    ],
    protocopts = ["--include_imports"],
)

envoy_proto_descriptor(
    name = "bookstore_proto_descriptor_bad",
    srcs = [
        "bookstore.proto",
    ],
    out = "bookstore_bad.descriptor",
    external_deps = [
        "http_api_protos",
        "well_known_protos",
    ],
)
