Add example of rules_foreign_cc with asan issue

This repo shows a bug using rules_foreign_cc with asan.

This build will succeed:
 bazel build --incompatible_enable_cc_toolchain_resolution  //:main_make

This build will fail:
 bazel build --incompatible_enable_cc_toolchain_resolution
 --features=asan //:main_make

This fails as `make` is built and linked with `-fsanitize=address`, and
a memory leak is detected when running `make` to build the program.

There doesn't seem to be a way to prevent just `make` from being built
with this option.
