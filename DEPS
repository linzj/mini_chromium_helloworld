# Copyright 2014 The Crashpad Authors
#
# Licensed under the Apache License, Version 2.0 (the "License");
# you may not use this file except in compliance with the License.
# You may obtain a copy of the License at
#
#     http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing, software
# distributed under the License is distributed on an "AS IS" BASIS,
# WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
# See the License for the specific language governing permissions and
# limitations under the License.

vars = {
  'chromium_git': 'https://chromium.googlesource.com',
  'gn_version': 'git_revision:5e19d2fb166fbd4f6f32147fbb2f497091a54ad8',
  # ninja CIPD package version.
  # https://chrome-infra-packages.appspot.com/p/infra/3pp/tools/ninja
  'ninja_version': 'version:2@1.8.2.chromium.3',
  'pull_linux_clang': False,
  'pull_win_toolchain': False,
  # Controls whether crashpad/build/ios/setup-ios-gn.py is run as part of
  # gclient hooks. It is enabled by default for developer's convenience. It can
  # be disabled with custom_vars (done automatically on the bots).
  'run_setup_ios_gn': True,
}

deps = {
  'buildtools':
      Var('chromium_git') + '/chromium/src/buildtools.git@' +
      '8b16338d17cd71b04a6ba28da7322ab6739892c2',
  'mini_chromium_helloworld/third_party/mini_chromium/mini_chromium':
      Var('chromium_git') + '/chromium/mini_chromium@' +
      '4332ddb6963750e1106efdcece6d6e2de6dc6430',

  # CIPD packages.
  'buildtools/linux64': {
    'packages': [
      {
        'package': 'gn/gn/linux-amd64',
        'version': Var('gn_version'),
      }
    ],
    'dep_type': 'cipd',
    'condition': 'host_os == "linux"',
  },
  'buildtools/mac': {
    'packages': [
      {
        'package': 'gn/gn/mac-${{arch}}',
        'version': Var('gn_version'),
      }
    ],
    'dep_type': 'cipd',
    'condition': 'host_os == "mac"',
  },
  'buildtools/win': {
    'packages': [
      {
        'package': 'gn/gn/windows-amd64',
        'version': Var('gn_version'),
      }
    ],
    'dep_type': 'cipd',
    'condition': 'host_os == "win"',
  },
}

recursedeps = [
  'buildtools',
]
