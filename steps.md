# build first

rustup target add thumbv7em-none-eabihf

cargo build --target thumbv7em-none-eabihf

# can build the true
rustup +nightly component add rust-src
cargo +nightly build -Z build-std=core,compiler_builtins --target x86_64-mini_os.json


# Run kernel
```
cargo install bootimage
rustup component add llvm-tools-preview
```

the image location
```
target/x86_64-mini_os/debug/bootimage-mini_os.bin
```

Run in QEMU:
```
qemu-system-x86_64 -drive format=raw,file=target/x86_64-mini_os/debug/bootimage-mini_os.bin
```
