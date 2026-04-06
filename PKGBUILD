# SPDX-License-Identifier: AGPL-3.0

#    ----------------------------------------------------------------------
#    Copyright © 2024, 2025, 2026  Pellegrino Prevete
#
#    All rights reserved
#    ----------------------------------------------------------------------
#
#    This program is free software: you can redistribute it and/or modify
#    it under the terms of the GNU Affero General Public License as
#    published by the Free Software Foundation, either version 3 of the
#    License, or (at your option) any later version.
#
#    This program is distributed in the hope that it will be useful,
#    but WITHOUT ANY WARRANTY; without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#    GNU Affero General Public License for more details.
#
#    You should have received a copy of the GNU Affero General Public
#    License along with this program.
#    If not, see <https://www.gnu.org/licenses/>.

# Maintainers:
#   Truocolo
#     <truocolo@aol.com>
#     <truocolo@0x6E5163fC4BFc1511Dbe06bB605cc14a3e462332b>
#   Pellegrino Prevete (dvorak)
#     <pellegrinoprevete@gmail.com>
#     <dvorak@0x87003Bd6C074C713783df04f36517451fF34CBEf>
# Contributors:
#   David Runge
#     <dvzrv@archlinux.org>
#   Sébastien Luttringer
#   Tom Gundersen
#     <teg@jklm.no>

_os="$(
  uname \
    -o)"
_evmfs_available="$(
  command \
    -v \
    "evmfs" || \
    true)"
if [[ ! -v "_evmfs" ]]; then
  if [[ "${_evmfs_available}" != "" ]]; then
    _evmfs="true"
  elif [[ "${_evmfs_available}" == "" ]]; then
    _evmfs="false"
  fi
fi
if [[ ! -v "_distro" ]]; then
  _distro="dogeos"
fi
if [[ ! -v "_ns" ]]; then
  _ns="themartiancompany"
fi
if [[ ! -v "_git" ]]; then
  _git="true"
fi
if [[ ! -v "_git_service" ]]; then
  _git_service="github"
fi
if [[ ! -v "_archive_format" ]]; then
  if [[ "${_git}" == "true" ]]; then
    if [[ "${_evmfs}" == "true" ]]; then
      _archive_format="bundle"
    elif [[ "${_evmfs}" == "false" ]]; then
      _archive_format="git"
    fi
  elif [[ "${_git}" == "false" ]]; then
    if [[ "${_git_service}" == "github" ]]; then
      _archive_format="zip"
    elif [[ "${_git_service}" == "gitlab" ]]; then
      _archive_format="tar.gz"
    fi
  fi
fi
_pkg=filesystem
pkgbase="${_pkg}"
pkgname=(
  "${pkgbase}"
)
pkgver=2026.04.05
_commit_distro="fc09643d8bb9c17fca17728e221aa9b43a1a9c1d"
pkgrel=6
pkgdesc='Base DogeOS files'
arch=(
  'any'
)
license=(
  "AGPL3"
)
_http="https://${_git_service}.com"
url="${_http}/${_ns}/${_distro}"
depends=(
  'iana-etc'
)
makedepends=(
  "coreutils"
)
if [[ "${_os}" == "Android" ]]; then
  provides=(
    "resolv-conf"
  )
fi
backup=(
  'etc/crypttab'
  'etc/fstab'
  'etc/group'
  'etc/gshadow'
  'etc/host.conf'
  'etc/hosts'
  'etc/issue'
  'etc/ld.so.conf'
  'etc/nsswitch.conf'
  'etc/passwd'
  'etc/profile'
  'etc/resolv.conf'
  'etc/securetty'
  'etc/shadow'
  'etc/shells'
  'etc/subgid'
  'etc/subuid'
)
source=(
  'COPYING'
  "${_distro}-release"
  'crypttab'
  'env-generator'
  'fstab'
  'group'
  'gshadow'
  'host.conf'
  'hosts'
  'issue'
  'ld.so.conf'
  'locale.sh'
  'nsswitch.conf'
  'os-release'
  'passwd'
  'profile'
  'resolv.conf'
  'securetty'
  'shadow'
  'shells'
  'sysctl'
  'sysusers'
  'tmpfiles'
  'subgid'
  'subuid'
)
sha256sums=(
  '7056c04df17a4e0f0bac9f787f347c9cd892cee6323d1c89528090afd0b934a3'
  '01ba4719c80b6fe911b091a7c05124b64eeece964e09c058ef8f9805daca546b'
  'e03bede3d258d680548696623d5979c6edf03272e801a813c81ba5a5c64f4f82'
  'ed0cb4f1db4021f8c3b5ce78fdf91d2c0624708f58f36c9cf867f4d93c3bc6da'
  'e54626e74ed8fee4173b62a545ab1c3a3a069e4217a0ee8fc398d9933e9c1696'
  '7a696fcfba89a55a6d73fa1a03c7f071fad2141340027b17a25db249e26b9be8'
  '25826e1050871d3ad9bb3ac4e8e2d6b27b4f2e34bc59c76e316f785b9da0a68f'
  '4d7b647169063dfedbff5e1e22cee77bd1a4183dbcfd5e802e68939da4bbf733'
  '10189cc7cf9dd18982685717a27274f1b7e416cbdd977b11538a720fa7eb4465'
  'fcb6d3b106c0c5966ee5a87499da0eeb14e3c24329d132c1efca80c75de39524'
  '785c6c3614a27ae6115a27c1ca55bbf333654780997c4ba7e181172b021d1bf3'
  '153d848ed51f2774e5a1578ea08e0c8586ecc63f7562697e035b84247edb2f82'
  'c8ee7a9faf798caab178ec51afae4146f1efd8a716b7acedf28345b6c75f9697'
  '71ff7a6e248d9a0718344c957ec709cb6f0b18631682fa404d7cff2af3ff341d'
  '13e2783884783ef46b8345fbcdf7880f0414c0a9c42e2b2fc6a2b048cbc2d86e'
  '1979ee468511e65109234d9ab7f26e84f0f5f2a96c3ce18740d145049cfa43f4'
  '5557d8e601b17a80d1ea7de78a9869be69637cb6a02fbfe334e22fdf64e61d4c'
  'd88be2b45b43605ff31dd83d6a138069b6c2e92bc8989b7b9ab9eba8da5f8c7b'
  '6e13705ac4d6f69cdba118c6b70c722346fd3c45224133e6bbfe28aca719563c'
  'ec289c03aa0d150e90e8287f001c8e6552ab9dd54f450bdb5c2d2254e477965b'
  '3c89c201db78414ad04621c1b2adc3df6e63be6a3046f155d741bcb8436b5a84'
  '66a8eb40762f45fed8720ee6c1ff5c1a3a654cc3ac03c87739c4cb4084dc482f'
  'f1b45f29b1a6b6796190bea821aebdd85ea5107115d6e95a4f9f2f5c9292b575'
  'e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855'
  'e3b0c44298fc1c149afbf4c8996fb92427ae41e4649b934ca495991b7852b855'
)
_tag_name="commit"
_tag_distro=${_commit_distro}
_tarname_distro="${_distro}-data-${_tag_distro}"
_tarfile_distro="${_tarname_distro}.${_archive_format}"
_distro_sum="1026f0c8a41733cb07edb493d8ad636abe11f67b5ee1ae3480921642c2e48cdd"
_distro_sig_sum="f3b50c8207b664fb61571262dcd437337cadec512e8b45c80b974337bf093bbb"
_distro_url="${_http}/${_ns}/${_distro}-data"
# Dvorak
_evmfs_ns="0x87003Bd6C074C713783df04f36517451fF34CBEf"
# Gnosis
_evmfs_network="100"
_evmfs_address="0x69470b18f8b8b5f92b48f6199dcb147b4be96571"
_evmfs_dir="evmfs://${_evmfs_network}/${_evmfs_address}/${_evmfs_ns}"
_distro_uri="${_evmfs_dir}/${_distro_sum}"
_distro_src="${_tarfile_distro}::${_distro_uri}"
_distro_sig_uri="${_evmfs_dir}/${_distro_sig_sum}"
_distro_sig_src="${_tarfile_distro}.sig::${_distro_sig_uri}"
if [[ "${_evmfs}" == "true" ]]; then
  if [[ "${_git}" == "false" ]]; then
    _msg=(
      "Not supported."
    )
    echo \
      "${_msg[*]}" \
      1>&2
    exit \
      1
  elif [[ "${_git}" == "true" ]]; then
    source+=(
      "${_distro_src}"
      "${_distro_sig_src}"
    )
    sha256sums+=(
      "${_distro_sum}"
      "${_distro_sig_sum}"
    )
  fi
elif [[ "${_evmfs}" == "false" ]]; then
  if [[ "${_git}" == true ]]; then
    _distro_src="${_tarname_distro}::git+${_distro_url}#${_tag_name}=${_tag_distro}"
    _distro_sum="SKIP"
  elif [[ "${_git}" == false ]]; then
    if [[ "${_git_service}" == "github" ]]; then
      if [[ "${_tag_name}" == "commit" ]]; then
        _uri="${_distro_url}/archive/${_commit_distro}.${_archive_format}"
        _distro_sum="SKIP"
      elif [[ "${_tag_name}" == "pkgver" ]]; then
        _msg=(
          "Not supported."
        )
        echo \
          "${_msg[*]}" \
          1>&2
      fi
    elif [[ "${_git_service}" == "gitlab" ]]; then
      if [[ "${_tag_name}" == "commit" ]]; then
        _uri="${_distro_url}/-/archive/${_tag_distro}/${_tag_distro}.${_archive_format}"
      fi
    fi
    _distro_src="${_tarfile_distro}::${_uri}"
  fi
  source+=(
    "${_distro_src}"
  )
  sha256sums+=(
    "${_distro_sum}"
  )
fi

_git_unbundle() {
  local \
    _tarname="${1}" \
    _bundle \
    _repo \
    _msg=()
  _bundle="${srcdir}/${_tarname}.bundle"
  _repo="${srcdir}/${_tarname}"
  _msg=(
    "Cloning '${_bundle}' into '${_repo}'."
  )
  msg \
    "${_msg[*]}"
  git \
    clone \
      "${_bundle}" \
      "${_repo}" || \
  git \
    -C \
      "${_repo}" \
      pull || \
  true
}

prepare() {
  local \
    _commit_hash
  if [[ "${_evmfs}" == "true" ]]; then
    if [[ "${_git}" == "false" ]]; then
      ur \
        "${_like}"
    elif [[ "${_git}" == "true" ]]; then
      _git_unbundle \
        "${_tarname}"
      if [[ "${_boost_oldest}" == "1.89" ]]; then
        _git_unbundle_update \
          "${srcdir}/${_tarname}" \
          "${srcdir}/${_pkg}-${_0_8_30_1_commit}"
      fi
    fi
  fi
  mv \
    "${_tarname}/"*".png" \
    "${srcdir}"
}

package() {
  local \
    group \
    link \
    mode \
    source_file \
    user
  declare \
    -A \
    directories
  declare \
    -A \
    files
  declare \
    -A \
    symlinks
  # associative array with directories and their assigned mode, user and group
  # all paths are relative to the root directory /
  directories=(
    ["boot"]="755:0:0"
    ["dev"]="755:0:0"
    ["etc"]="755:0:0"
    ["etc/ld.so.conf.d"]="755:0:0"
    ["etc/profile.d"]="755:0:0"
    ["etc/skel"]="755:0:0"
    ["home"]="755:0:0"
    ["mnt"]="755:0:0"
    ["opt"]="755:0:0"
    ["proc"]="555:0:0"
    ["root"]="0750:0:0"
    ["run"]="755:0:0"
    ["srv/http"]="755:0:0"
    ["srv/ftp"]="555:0:11"  # vsftpd won't run with write perms on /srv/ftp
    ["sys"]="555:0:0"
    ["tmp"]="1777:0:0"
    ["usr"]="755:0:0"
    ["usr/bin"]="755:0:0"
    ["usr/include"]="755:0:0"
    ["usr/lib"]="755:0:0"
    ["usr/lib/ld.so.conf.d"]="755:0:0"
    ["usr/local/bin"]="755:0:0"
    ["usr/local/etc"]="755:0:0"
    ["usr/local/games"]="755:0:0"
    ["usr/local/include"]="755:0:0"
    ["usr/local/lib"]="755:0:0"
    ["usr/local/man"]="755:0:0"
    ["usr/local/sbin"]="755:0:0"
    ["usr/local/share"]="755:0:0"
    ["usr/local/src"]="755:0:0"
    ["usr/share/factory/etc"]="755:0:0"
    ["usr/share/man/man1"]="755:0:0"
    ["usr/share/man/man2"]="755:0:0"
    ["usr/share/man/man3"]="755:0:0"
    ["usr/share/man/man4"]="755:0:0"
    ["usr/share/man/man5"]="755:0:0"
    ["usr/share/man/man6"]="755:0:0"
    ["usr/share/man/man7"]="755:0:0"
    ["usr/share/man/man8"]="755:0:0"
    ["usr/share/misc"]="755:0:0"
    ["usr/share/pixmaps"]="755:0:0"
    ["usr/src"]="755:0:0"
    ["var"]="755:0:0"
    ["var/cache"]="755:0:0"
    ["var/empty"]="755:0:0"
    ["var/games"]="775:0:50"  # allow setgid games (gid 50) to write scores
    ["var/lib/misc"]="755:0:0"
    ["var/local"]="755:0:0"
    ["var/log/old"]="755:0:0"
    ["var/opt"]="755:0:0"
    ["var/spool/mail"]="1777:0:0"
    ["var/tmp"]="1777:0:0"
  )
  # associative array with symlink names and their respective targets
  # all paths are relative to the root directory /
  symlinks=(
    ["bin"]="usr/bin"
    ["etc/mtab"]="../proc/self/mounts"
    ["lib"]="usr/lib"
    ["sbin"]="usr/bin"
    ["usr/local/share/man"]="../man"
    ["usr/sbin"]="bin"
    ["var/lock"]="../run/lock"
    ["var/mail"]="spool/mail"
    ["var/run"]="../run"
  )
  if [[ $CARCH = 'x86_64' ]]; then
    symlinks["lib64"]="usr/lib"
    symlinks["usr/lib64"]="lib"
  fi
  # associative array of target files, their source file, file mode, user and group ownership
  files=(
    ["etc/${_distro}-release"]="${_distro}-release:644:0:0"
    ["etc/crypttab"]="crypttab:600:0:0"
    ["etc/fstab"]="fstab:644:0:0"
    ["etc/group"]="group:644:0:0"
    ["etc/gshadow"]="gshadow:600:0:0"
    ["etc/host.conf"]="host.conf:644:0:0"
    ["etc/hosts"]="hosts:644:0:0"
    ["etc/issue"]="issue:644:0:0"
    ["etc/ld.so.conf"]="ld.so.conf:644:0:0"
    ["etc/nsswitch.conf"]="nsswitch.conf:644:0:0"
    ["etc/passwd"]="passwd:644:0:0"
    ["etc/profile"]="profile:644:0:0"
    ["etc/profile.d/locale.sh"]="locale.sh:644:0:0"
    ["etc/resolv.conf"]="resolv.conf:644:0:0"
    ["etc/securetty"]="securetty:644:0:0"
    ["etc/shells"]="shells:644:0:0"
    ["etc/shadow"]="shadow:600:0:0"
    ["etc/subgid"]="subgid:644:0:0"
    ["etc/subuid"]="subuid:644:0:0"
    ["usr/lib/os-release"]="os-release:644:0:0"
    ["usr/lib/sysctl.d/10-${_distro}.conf"]="sysctl:644:0:0"
    ["usr/lib/sysusers.d/${_distro}.conf"]="sysusers:644:0:0"
    ["usr/lib/tmpfiles.d/${_distro}.conf"]="tmpfiles:644:0:0"
    ["usr/lib/systemd/system-environment-generators/10-${_distro}"]="env-generator:755:0:0"
    ["usr/share/factory/etc/${_distro}-release"]="${_distro}-release:644:0:0"
    ["usr/share/factory/etc/crypttab"]="crypttab:600:0:0"
    ["usr/share/factory/etc/fstab"]="fstab:644:0:0"
    ["usr/share/factory/etc/group"]="group:644:0:0"
    ["usr/share/factory/etc/gshadow"]="gshadow:600:0:0"
    ["usr/share/factory/etc/host.conf"]="host.conf:644:0:0"
    ["usr/share/factory/etc/hosts"]="hosts:644:0:0"
    ["usr/share/factory/etc/issue"]="issue:644:0:0"
    ["usr/share/factory/etc/ld.so.conf"]="ld.so.conf:644:0:0"
    ["usr/share/factory/etc/nsswitch.conf"]="nsswitch.conf:644:0:0"
    ["usr/share/factory/etc/passwd"]="passwd:644:0:0"
    ["usr/share/factory/etc/profile"]="profile:644:0:0"
    ["usr/share/factory/etc/profile.d/locale.sh"]="locale.sh:644:0:0"
    ["usr/share/factory/etc/resolv.conf"]="resolv.conf:644:0:0"
    ["usr/share/factory/etc/securetty"]="securetty:644:0:0"
    ["usr/share/factory/etc/shadow"]="shadow:600:0:0"
    ["usr/share/factory/etc/shells"]="shells:644:0:0"
    ["usr/share/factory/etc/subgid"]="subgid:644:0:0"
    ["usr/share/factory/etc/subuid"]="subuid:644:0:0"
    ["usr/share/pixmaps/${_distro}.png"]="${_distro}.png:644:0:0"
    ["usr/share/pixmaps/${_distro}-landscape.png"]="${_distro}-landscape.png:644:0:0"
  )
  cd \
    "${pkgdir}"
  for dir in "${!directories[@]}"; do
    IFS=':' \
    read \
      mode \
      user \
      group <<< \
      "${directories[$dir]}"
    install \
      -vdm \
      "${mode}" \
      -o \
        "${user}" \
      -g \
        "$group" \
      "${dir}"
  done
  for link in "${!symlinks[@]}"; do
    ln \
      -sv \
      "${symlinks[$link]}" \
      "${link}"
  done
  for target_file in "${!files[@]}"; do
    IFS=':'
    read \
      source_file \
      mode \
      user \
      group <<< \
      "${files[$target_file]}"
    install \
      -vDm \
      "${mode}" \
      -o \
        "${user}" \
      -g \
        "${group}" \
      "${srcdir}/${source_file}" \
      "${target_file}"
  done
  install \
    -vDm644 \
    "${srcdir}/COPYING" \
    -t \
    "${pkgdir}/usr/share/licenses/${pkgname}/"
}

# vim:set ts=2 sw=2 et:
