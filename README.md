## Requirements:

0. You need Rust version 1.64 or higher to compile.

## Install

Using Cargo to install (requires ~/.cargo/bin to be in PATH)

```bash
cargo install rana
```

### Compile and execute it:

To compile on Ubuntu/Pop!\_OS/Debian, please install [cargo](https://www.rust-lang.org/tools/install), then run the following commands:

```bash
sudo apt update
sudo apt install -y cmake build-essential
```

Then clone the repo, build and run:

```bash
git clone https://github.com/vortelus/mining-tool.git
cd rana
cargo run --release
```

By default it will generate a public key with a difficulty of `10` but you can customize its difficulty or vanity prefix with the proper parameters.

### Searching for multiple vanity targets at once

Specifying multiple `vanity-n-*` targets allows you to leverage the work you've already done to generate each new `npub` candidate. Searching a candidate `npub` for additional targets is incredibly fast because it's just a trivial string compare.

Statistically speaking, searching for `rana,h0dl` should take half the time that searching for `rana` and then doing a second, separate search for `hodl` would take.
