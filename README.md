SSH access to Windows/Linux/MacOS/BSD runners
=============================================

GitHub offers unlimited and free CI minutes to all public repositories.

This repository contains a GitHub workflow spawning jobs for all available
public runners, with ssh access to them using [action-tmate](https://github.com/mxschmitt/action-tmate).

1. Fork this repo
2. Enable actions on your fork: Actions -> enable
3. Trigger a workflow manually: Actions -> build.yml -> Run workflow (master)
4. Go to any job, see the ssh command, and connect using your GitHub ssh key.

Note: All jobs will timeout after 6 hours, or end once you logout from the
machine.

Supported x86_64 runners:
- freebsd (using [freebsd-vm](https://github.com/vmactions/freebsd-vm))
- haiku (using [haiku-vm](https://github.com/vmactions/haiku-vm))
- macos-15-intel
- netbsd (using [netbsd-vm](https://github.com/vmactions/netbsd-vm))
- openbsd (using [openbsd-vm](https://github.com/vmactions/openbsd-vm))
- ubuntu-24.04
- windows-2025

Supported arm64 runners:
- ubuntu-24.04-arm
- macos-26
- windows-11-arm

Note: for bsd and haiku runners, you get an access to linux runner, and need to
use `ssh freebsd`, `ssh netbsd`, `ssh openbsd` or `ssh haiku` to access vm.
