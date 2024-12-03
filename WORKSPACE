load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "io_bazel_rules_go",
    sha256 = "6dc2da7ab4cf5d7bfc7c949776b1b7c733f05e56edc4bcd9022bb249d2e2a996",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/rules_go/releases/download/v0.39.1/rules_go-v0.39.1.zip",
        "https://github.com/bazelbuild/rules_go/releases/download/v0.39.1/rules_go-v0.39.1.zip",
    ],
)

http_archive(
    name = "bazel_gazelle",
    sha256 = "727f3e4edd96ea20c29e8c2ca9e8d2af724d8c7778e7923a854b2c80952bc405",
    urls = [
        "https://mirror.bazel.build/github.com/bazelbuild/bazel-gazelle/releases/download/v0.30.0/bazel-gazelle-v0.30.0.tar.gz",
        "https://github.com/bazelbuild/bazel-gazelle/releases/download/v0.30.0/bazel-gazelle-v0.30.0.tar.gz",
    ],
)

http_archive(
    name = "com_google_protobuf",
    sha256 = "72bae766561149f8507a81647f91fc519d2a60309613f004ed307cb5f9b1242b",
    strip_prefix = "protobuf-23.1",
    urls = [
        "https://github.com/protocolbuffers/protobuf/releases/download/v23.1/protobuf-23.1.tar.gz",
    ],
)

load("@io_bazel_rules_go//go:deps.bzl", "go_register_toolchains", "go_rules_dependencies")
load("@bazel_gazelle//:deps.bzl", "gazelle_dependencies", "go_repository")
load("@com_google_protobuf//:protobuf_deps.bzl", "protobuf_deps")
load("//:deps.bzl", "go_dependencies")

go_repository(
    name = "com_github_ettle_strcase",
    importpath = "github.com/ettle/strcase",
    sum = "h1:fGNiVF21fHXpX1niBgk0aROov1LagYsOwV/xqKDKR/Q=",
    version = "v0.2.0",
)

go_register_toolchains(version = "1.20.4")

go_rules_dependencies()

gazelle_dependencies()

# gazelle:repository_macro deps.bzl%go_dependencies
go_dependencies()

protobuf_deps()
