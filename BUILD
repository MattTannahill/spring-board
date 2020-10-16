load("@rules_java//java:defs.bzl", "java_binary", "java_library", "java_test")

package(default_visibility = ["//visibility:public"])

java_library(
    name = "spring-board-lib",
    srcs = glob(["src/main/java/com/MattTannahill/spring_board/*.java"]),
    resources = glob(["src/main/resources/**"]),
    deps = [
        "@maven//:org_springframework_boot_spring_boot",
        "@maven//:org_springframework_boot_spring_boot_autoconfigure"
    ],
)

java_binary(
    name = "spring-board",
    main_class = "com.MattTannahill.spring_board.SpringBoardApplication",
    runtime_deps = [
        "@maven//:org_springframework_boot_spring_boot_starter_web",
        ":spring-board-lib"
    ],
)

load("//:junit5.bzl", "java_junit5_test")

java_junit5_test(
    name = "spring-board-test",
    srcs = glob(["src/test/java/com/MattTannahill/spring_board/*.java"]),
    test_package = "com.MattTannahill.spring_board",
    deps = [
        "@maven//:org_springframework_boot_spring_boot_test",
    ],
    runtime_deps = [
        "@maven//:org_springframework_boot_spring_boot_starter_test",
        ":spring-board-lib"
    ],
)