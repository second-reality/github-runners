SSH access to Windows/Linux/MacOS/BSD runners
=============================================

GitHub offers unlimited and free CI minutes to all public repositories.

This repository contains a GitHub workflow spawning jobs for all available
public runners, with ssh access to them using [action-tmate](https://github.com/mxschmitt/action-tmate).

1. Fork this repo
2. Enable actions on your fork: Actions -> enable
3. Trigger a workflow manually: Actions -> build.yml -> Run workflow (master)
4. Go to any job, see the ssh command, and connect using your GitHub ssh key
5. Jobs will timeout after 6 hours, or end once you logout from the machine

**NOTE: for bsd runners, you get an access to linux runner, and need to
use `ssh freebsd`, `ssh netbsd` or `ssh openbsd` to access VM.**

**NOTE: for windows runners, tmate forces a MINGW64 shell by default. Use `bash`
(without parameters) another time to access correct environment.**

Supported x86_64 runners:
- freebsd (using [freebsd-vm](https://github.com/vmactions/freebsd-vm))
- macos-15-intel
- netbsd (using [netbsd-vm](https://github.com/vmactions/netbsd-vm))
- openbsd (using [openbsd-vm](https://github.com/vmactions/openbsd-vm))
- ubuntu-24.04
- windows-2025 (msys2 mingw64, ucrt64 and clang64 environments)

Supported arm64 runners:
- ubuntu-24.04-arm
- macos-26
- windows-11-arm (msys2 clangarm64 environment)

This repository is mostly used to provide runners for QEMU, thus it install
build dependencies by default.
