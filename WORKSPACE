workspace(
    name = "gql_gen_repro",
    managed_directories = {
        "@npm": ["node_modules"],
    },
)

load("@bazel_tools//tools/build_defs/repo:http.bzl", "http_archive")

http_archive(
    name = "build_bazel_rules_nodejs",
    sha256 = "d0c4bb8b902c1658f42eb5563809c70a06e46015d64057d25560b0eb4bdc9007",
    urls = ["https://github.com/bazelbuild/rules_nodejs/releases/download/1.5.0/rules_nodejs-1.5.0.tar.gz"],
)

load("@build_bazel_rules_nodejs//:index.bzl", "node_repositories", "yarn_install")

yarn_install(
    name = "npm",
    args = [
        "--frozen-lockfile",
    ],
    data = [
    ],
    package_json = "//:package.json",
    yarn_lock = "//:yarn.lock",
)

node_repositories(package_json = ["//:package.json"])

load("@npm//:install_bazel_dependencies.bzl", npm_install_bazel_dependencies = "install_bazel_dependencies")

npm_install_bazel_dependencies()
