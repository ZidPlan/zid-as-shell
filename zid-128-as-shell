#!/bin/sh

##
# zid-as-shell
#
# Generate a Zen identifier (http://www.zidplan.com)
# wit implementation as a shell script.
#
# Usage:
#
#     zid-as-shell
#
# Example:
#
#     $ zid-as-shell
#     0cb49f132271bf0436a8f0689f87ee9c
#
# ## Solutions ##
#
# Solution via hexdump command:
#
#     bits=${1-128}
#     n=$(expr $bits / 8)
#     hexdump -n $n -v -e '/1 "%02x"' -e "/$n \"\n\"" /dev/urandom
#
# Solution for Linux via tr command:
#
#     bits=${1-128}
#     n=$(expr $bits / 8)
#     cat /dev/urandom | tr -cd '0-9a-f' | head -c "$n"; echo
#
# Solution for BSD and macOS via tr command:
#
#     bits=${1-128}
#     n=$(expr $bits / 8)
#     cat /dev/urandom | env LC_CTYPE=C tr -cd '0-9a-f' | head -c "$n"; echo
#
#
# This implementation uses the commands `hexdump` and `/dev/urandom`.
#
# ## Tracking ##
#
#   * Command: zid-as-shell
#   * Version: 5.0.0
#   * Created: 2015-01-25
#   * Updated: 2022-07-25T20:20:20Z
#   * License: GPL-2.0-or-later or contact us for custom
#   * Contact: Joel Parker Henderson (joel@joelparkerhenderson.com)
##
set -euf
bits=${1-128}
n=$(expr $bits / 8)
hexdump -n $n -v -e '/1 "%02x"' -e "/$n \"\n\"" /dev/urandom
