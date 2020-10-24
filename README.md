# Kernel version 4.14.x
This branch is used to provide Rancher OS 1.5.x compatible 4.14.x version kernels.

On this branch we do NOT provide new features but instead of keep changes on minimal and just bump kernel patch versions.
If you are looking for new features then check [v5.9.x branch](https://github.com/burmilla/os-kernel/tree/v5.9.x).

## How to contribute
- Fork this repository and create new branch based on v4.14.x branch.
- Check from [kernel.org](https://www.kernel.org/) that what is latest 4.14.x kernel version.
- Run kernel configuration with commands (update version to KERNEL_TAG):
```bash
KERNEL_TAG=4.14.? MENUCONFIG=true OVERRIDE_KERNEL_ARCH=x86 make kernel-config
```
- Save changes over .config
- Copy new config version over to one which is stored to GIT:
```bash
cp dist/kernel/config config/x86/kernel-config
```
- Update modules/x86/modules.list / modules-extra.list if new modules was found
- Test build kernel with command:
```bash
KERNEL_TAG=4.14.? make release
```

# License
Copyright (c) 2020 Project Burmilla

Copyright (c) 2014-2020 [Rancher Labs, Inc.](http://rancher.com)

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

[http://www.apache.org/licenses/LICENSE-2.0](http://www.apache.org/licenses/LICENSE-2.0)

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
