load(":cc_toolchain_config.bzl", "cc_toolchain_config")

package(default_visibility = ["//visibility:public"])

cc_toolchain_config(
    name = "k8_toolchain_config",
)

filegroup(
    name = "empty",
    srcs = [],  # bazel crashes without this
    output_licenses = ["unencumbered"],
)

filegroup(
    name = "compiler_files",
    srcs = [
        ":includes",
    ],
    output_licenses = ["unencumbered"],
)

cc_toolchain(
    name = "k8_toolchain",
    all_files = ":empty",
    compiler_files = ":empty",
    dwp_files = ":empty",
    linker_files = ":empty",
    objcopy_files = ":empty",
    strip_files = ":empty",
    supports_param_files = 0,
    toolchain_config = ":k8_toolchain_config",
    toolchain_identifier = "k8-toolchain",
)

cc_toolchain_suite(
    name = "clang_suite",
    toolchains = {
        "k8": ":k8_toolchain",
    },
)
