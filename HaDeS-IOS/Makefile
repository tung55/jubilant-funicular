name: Build HaDeS-IOS Kernel

on:
  push:
    branches: [ "main" ]
  pull_request:
    branches: [ "main" ]

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout repository
      uses: actions/checkout@v4

    - name: Install Build Dependencies
      run: |
        sudo apt-get update
        sudo apt-get install -y build-essential gcc-multilib nasm make grub-pc-bin xorriso

    - name: Compile Project in HaDeS-IOS
      run: |
        cd HaDeS-IOS
        make

    - name: Upload ISO Artifact
      uses: actions/upload-artifact@v4
      with:
        name: myos-iso
        path: HaDeS-IOS/myos.iso
