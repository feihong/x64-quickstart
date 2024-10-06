# Feihong's x86-64 Quickstart

## Install on M1 Mac

Run to verify that you have developer tools installed:

    clang -v

If you don't have them installed, it will prompt you to install them.

Open x64 shell:

    arch -x86_64 zsh

In x64 shell, running `gcc -v` should print something like this:

    Apple clang version 15.0.0 (clang-1500.3.9.4)
    Target: x86_64-apple-darwin23.6.0
    Thread model: posix
    InstalledDir: /Library/Developer/CommandLineTools/usr/bin

In case `arch` command doesn't work, install Rosetta:

    softwareupdate --install-rosetta --agree-to-license

## Commands

Dump assembly for `return_2.c` to `return_2.s`:

    gcc -S -O -fno-asynchronous-unwind-tables -fcf-protection=none return_2.c

Compile `return_2.s` into `return_2` executable and run it:

    gcc return_2.s -o return_2
    ./return_2
    echo $?
