package(default_visibility = ["//visibility:public"])

load(
    "@io_bazel_rules_go//go:def.bzl",
    "go_library",
    "go_test",
)

go_library(
    name = "go_default_library",
    srcs = ["fuzzer.go"],
    importpath = "k8s.io/kubernetes/cmd/kubeadm/app/apis/output/fuzzer",
    deps = [
        "//cmd/kubeadm/app/apis/kubeadm/v1beta2:go_default_library",
        "//cmd/kubeadm/app/apis/output:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/apis/meta/v1:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/runtime/serializer:go_default_library",
        "//vendor/github.com/google/gofuzz:go_default_library",
    ],
)

filegroup(
    name = "package-srcs",
    srcs = glob(["**"]),
    tags = ["automanaged"],
    visibility = ["//visibility:private"],
)

filegroup(
    name = "all-srcs",
    srcs = [":package-srcs"],
    tags = ["automanaged"],
)

go_test(
    name = "go_default_test",
    srcs = ["fuzzer_test.go"],
    embed = [":go_default_library"],
    deps = [
        "//cmd/kubeadm/app/apis/output/scheme:go_default_library",
        "//staging/src/k8s.io/apimachinery/pkg/api/apitesting/roundtrip:go_default_library",
    ],
)
