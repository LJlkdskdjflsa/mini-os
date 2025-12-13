# mini-os

Tiny x86_64 bare-metal experiment based on bootloader-rs. Builds with nightly and a custom target spec.

## Building

- Install nightly with source: `rustup toolchain install nightly --component rust-src`
- Build core/compiler_builtins and kernel: `cargo +nightly build -Z build-std=core,compiler_builtins`

## Running in QEMU

- Install QEMU (macOS example): `brew install qemu`
- Boot the image: `qemu-system-x86_64 -drive format=raw,file=target/x86_64-mini_os/debug/bootimage-mini_os.bin`
