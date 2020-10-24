# Kernel version 5.9.x
This branch is used to provide 5.9.x version kernels.

On this branch we DO provide new features when ever users request them.
If you are looking for more stable version then check [v4.14.x branch](https://github.com/burmilla/os-kernel/tree/v4.14.x).

## How to contribute
- Fork this repository and create new branch based on 5.9.x branch.
- Check what is latest [firmware tag](https://git.kernel.org/pub/scm/linux/kernel/git/firmware/linux-firmware.git/refs/) and update FIRMWARE_TAG value Dockerfile.dapper
- Check from [kernel.org](https://www.kernel.org/) that what is latest 5.9.x kernel version.
- Run kernel configuration with commands (update version to KERNEL_TAG):
```bash
KERNEL_TAG=5.9.? MENUCONFIG=true OVERRIDE_KERNEL_ARCH=x86 make kernel-config
```
- Save changes over .config
- Copy new config version over to one which is stored to GIT:
```bash
cp dist/kernel/config config/x86/kernel-config
```
- Test build kernel with command:
```bash
KERNEL_TAG=5.9.? OVERRIDE_KERNEL_ARCH=x86 make release
```
- Update firmware/... files if build fails to `ERROR: Firmware ? in ? is not the latest - update to`
- Update modules/x86/modules.list / modules-extra.list if build fails to new modules was found error

## Contact
For bugs, questions, comments, corrections, suggestions, etc., open an issue in
 [burmilla/os](//github.com/burmilla/os/issues) with a title starting with `[os-base] `.

Or just [click here](//github.com/burmilla/os/issues/new?title=%5Bos-base%5D%20) to create a new issue.


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
