# shell-tap

Shell Tap is an autocomplete system for terminal usage.

## Who

Terminal emulator users running macOS or Linux

## What

An autocomplete system that uses the output of recent commands as autocomplete suggestions.

## How

* Wrap an existing shell like bash or zsh
* Assumption: shell's output/input are stdin/stdout to terminal emulator
* Capture the stdout of forked shell, forward it stdout, statefully parse it to understand what is plain text output and what's control codes, etc, and store keywords in a good data structure
* Forward all stdin to forked shell
* Use the contents of the data structure as suggestions for autocomplete
* Serve these suggestions via some RPC mechanism, files on disk, or UDS, or LSP, or ???
