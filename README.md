<div align="start">
  <h1>Kernel builder for MT6768</h1>
  <h3><i>Powered By GitHub Actions</i></h3>
</div>

## Usage Guide

> [!NOTE]
> You will need a GitHub account.

<details>
  <summary><i>Click to expand</i></summary>

> ### 1.
> ![01](guide/images/01.png)

> ### 2.
> ![02](guide/images/02.png)

> ### 3.
> ![03](guide/images/03.png)

> ### 4.
> ![04](guide/images/04.png)

> ### 5.
> ![05](guide/images/05.png)

> ### 6.
> ![06](guide/images/06.png)

> ### 7.
> ![07](guide/images/07.png)

> ### 8.
> ![08](guide/images/08.png)

> ### 9.
> ![09](guide/images/09.png)

> ### 10.
> ![10](guide/images/10.png)

> ### 11.
> ![11](guide/images/11.png)
> **Note:** Reload this page if the yellow circle does not appear.

> ### 12.
> ![12](guide/images/12.png)

> ### 13.
> ![13](guide/images/13.png)

> ### 14.
> ![14](guide/images/14.png)

</details>

## Options Guide

> [!NOTE]
> All options are located in [config.env](config.env)

<br>

| Base section options | Optional | Description | Example value |
|---------------------|----------|-------------|----------------|
| KERNEL_SOURCE | <div align="center">❌</div> | Link to kernel repository | `https://github.com/Jbub6/android_kernel_xiaomi_mt6768` |
| KERNEL_SOURCE_BRANCH | <div align="center">❌</div> | Branch name of kernel repository | <div align="center">`kernel-tree`</div> |
| KERNEL_ARCH | <div align="center">❌</div> | The Linux kernel architecture | <div align="center">`arm64`</div> |
| KERNEL_IMAGE_NAME | <div align="center">❌</div> | Format of the kernel image for flashable AnyKernel3 zip | <div align="center">`Image.gz-dtb`</div> |
| KERNEL_CONFIG_MONOLITHIC | <div align="center">❌</div> | WIP | <div align="center">`false`</div> |

<br>

| KernelSU section options | Optional | Description | Example value |
|--------------------------|----------|-------------|---------------|
| KERNELSU_ENABLE | <div align="center">✅</div> | Enables accounting for the KernelSU options written below | <div align="center">`true`</div> |
| KERNELSU_SETUP_SOURCE | <div align="center">❌</div> | Link to KernelSU setup script | `https://raw.githubusercontent.com/tiann/KernelSU/main/kernel/setup.sh` |
| KERNELSU_TAG | <div align="center">✅</div> | Repository branch or tag of KernelSU | <div align="center">`v1.0.1`</div> |
| KERNELSU_REVERT_GKI | <div align="center">✅</div> | Revert the [commit](https://github.com/tiann/KernelSU/commit/898e9d4f8ca9b2f46b0c6b36b80a872b5b88d899) that removed non-GKI kernel support | <div align="center">`true`</div> |
| KERNELSU_EXPECTED_SIZE | <div align="center">✅</div> | If not empty, this value will be set to KSU_EXPECTED_SIZE, see https://github.com/tiann/KernelSU/blob/main/kernel/Kbuild for more details | `0x033b` |
| KERNELSU_EXPECTED_HASH | <div align="center">✅</div> | If not empty, this value will be set to KSU_EXPECTED_HASH, see https://github.com/tiann/KernelSU/blob/main/kernel/Kbuild for more details | `c371061b19d8c7d7d6133c6a9bafe198fa944e50c1b31c9d8daa8d7f1fc2d2d6` |
> [!IMPORTANT]
> [KernelSU](https://kernelsu.org/guide/what-is-kernelsu.html) [no longer supports non-GKI kernels](https://github.com/tiann/KernelSU/issues/1705) after version [v1.0.0](https://github.com/tiann/KernelSU/releases/tag/v1.0.0). The last supported version is [v0.9.5](https://github.com/tiann/KernelSU/releases/tag/v0.9.5), please make sure to use the correct tag.

<br>

| APatch section options | Optional | Description | Example value |
|------------------------|----------|-------------|---------------|
| APATCH_ENABLE | <div align="center">✅</div> | Add [required configs](https://apatch.dev/install.html#install-requirements) for [APatch](https://apatch.dev/what-is-apatch.html) | <div align="center">`false`</div> |

<br>

| Compiler section options | Optional | Description | Example value |
|--------------------------|----------|-------------|---------------|
| CC_CLANG_ENABLE | <div align="center">✅</div> | Enable Clang toolchain usage and accounting for the Clang options written below | <div align="center">`true`</div> |
| CC_CLANG_SOURCE | <div align="center">❌</div> | Link to Clang archive or repository | `https://github.com/ZyCromerZ/Clang/releases/download/21.0.0git-20250415-release/Clang-21.0.0git-20250415.tar.gz` |
| CC_CLANG_BRANCH | <div align="center">✅</div> | Branch name of Clang repository | <div align="center">`main`</div> |
| CC_CMDS | <div align="center">❌</div> | Compiler options | `LLVM=1 LLVM_IAS=1 CROSS_COMPILE=aarch64-linux-gnu- CROSS_COMPILE_ARM32=arm-linux-gnueabi- CROSS_COMPILE_COMPAT=arm-linux-gnueabi- CONFIG_NO_ERROR_ON_MISMATCH=y TARGET_BUILD_VARIANT=user` |

<br>

| Anykernel3 section options | Optional | Description | Example value |
|----------------------------|----------|-------------|---------------|
| ANYKERNEL3_ENABLE | <div align="center">✅</div> | Enable creating flashable AnyKernel3 zip and accounting for the options written below | <div align="center">`true`</div> |
| ANYKERNEL3_SOURCE | <div align="center">❌</div> | Link to AnyKernel3 archive or repository | `https://github.com/Jbub6/AnyKernel3.git` |
| ANYKERNEL3_BRANCH | <div align="center">✅</div> | Branch name of AnyKernel3 repository | <div align="center">`photon`</div> |

<br>

| Misc section options | Optional | Description | Example value |
|-----------------------|----------|-------------|---------------|
| NEED_PYTHON2 | <div align="center">✅</div> | Many old kernels require python2 to build them | <div align="center">`false`</div> |
| NEED_SOME_PACKAGES | <div align="center">✅</div> | WIP | <div align="center">`false`</div> |

<br>

| Droidspaces section options | Optional | Description | Example value |
|-----------------------|----------|-------------|---------------|
| DROIDSPACES_ENABLE | <div align="center">✅</div> | Add [required configs](https://github.com/ravindu644/Droidspaces-OSS/blob/main/Documentation/Kernel-Configuration.md#step-1-the-required-options) and a [patch](https://github.com/ravindu644/Droidspaces-OSS/blob/main/Documentation/resources/kernel-patches/non-GKI/02.fix_restore%20cgroup%20file%20prefix%20handling%20.patch) for [Droidspaces](https://github.com/ravindu644/Droidspaces-OSS) | <div align="center">`false`</div> |

<br>

## Credits

- [dabao1955](https://github.com/dabao1955) for the structure of README.md
