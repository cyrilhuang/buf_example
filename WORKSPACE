workspace(name = "example")

load("@bazel_tools//tools/build_defs/repo:git.bzl", "git_repository")
load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

git_repository(
    name = "riegeli",
    commit = "904c0c263b8632265103f0066c168a92c7713b07",
    remote = "https://github.com/google/riegeli.git",
)

http_archive(
    name = "com_google_protobuf",
    patch_args = ["-p1"],
    patches = ["@riegeli//third_party:protobuf.patch"],
    sha256 = "cfcba2df10feec52a84208693937c17a4b5df7775e1635c1e3baffc487b24c9b",
    strip_prefix = "protobuf-3.9.2",
    urls = ["https://github.com/protocolbuffers/protobuf/archive/v3.9.2.zip"],  # 2019-09-20
)

http_archive(
    name = "zlib",
    build_file = "@riegeli//third_party:zlib.BUILD",
    sha256 = "c3e5e9fdd5004dcb542feda5ee4f0ff0744628baf8ed2dd5d66f8ca1197cb1a1",
    strip_prefix = "zlib-1.2.11",
    urls = ["http://zlib.net/fossils/zlib-1.2.11.tar.gz"],  # 2017-01-15
)
