# ESP UP

ESP32 dev environment setup memo.

## Steps on Ubuntu 24.04.1 LTS (GNU/Linux 6.8.0-51-generic aarch64)

- Install Dependencies
  ```shell
  sudo apt-get install -y libc6
  # https://github.com/esp-rs/espup
  sudo apt-get install -y gcc build-essential curl pkg-config
  # https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/linux-macos-setup.html#step-1-install-prerequisites
  sudo apt-get install -y git wget flex bison gperf python3 python3-pip python3-venv cmake ninja-build ccache libffi-dev libssl-dev dfu-util libusb-1.0-0
  # https://github.com/esp-rs/esp-idf-template#install-cargo-sub-commands
  sudo apt-get install -y libudev-dev
  ```
- Install [rust](https://rustup.rs/)
  ```shell
  curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
  source $HOME/.cargo/env
  ```
- Crates: https://github.com/esp-rs/esp-idf-template#install-cargo-sub-commands
  ```shell
  cargo install cargo-generate
  cargo install ldproxy
  cargo install espup
  cargo install espflash
  cargo install cargo-espflash
  ```
- ESPUP
  ```shell
  espup install
  source $HOME/export-esp.sh
  ```

## Create a New Project: https://github.com/esp-rs/esp-idf-template#generate-the-project

  ```shell
  cargo generate esp-rs/esp-idf-template cargo
  cd [project-name]
  cargo espflash flash --release --monitor
  ```

# Credits

- https://docs.esp-rs.org/book/writing-your-own-application/generate-project/index.html
- https://docs.espressif.com/projects/esp-idf/en/latest/esp32/get-started/linux-macos-setup.html#step-1-install-prerequisites
- https://github.com/esp-rs/esp-idf-template
- https://github.com/cargo-generate/cargo-generate
- https://github.com/esp-rs/espup
- https://github.com/esp-rs/std-training
