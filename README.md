# ACER-NITRO-AN515-58-MACOS-OPENCORE

Acer Nitro AN515-58 的 OpenCore 配置模板和 SSDT。原始 EFI 在 i7-12650H / RTX 4060 Laptop 机型上从外置 USB SSD 启动至 macOS Tahoe 26.7.1（25G241）桌面，使用 OpenCore 1.0.9。图形加速和 iServices 未完成验证。

## 重建 EFI

1. 用 [1401 v2.9](https://github.com/nullmoth/1401/releases/tag/v2.9) 扫描本机并生成 Tahoe EFI。原配置按外置系统盘生成，内置 NVMe 使用 Intel VMD。
2. 对照 [config.plist](EFI/OC/config.plist) 和 [SSDT](EFI/OC/ACPI) 检查设置。DSDT.aml 由本机生成。仓库模板里的 SystemSerialNumber、MLB、SystemUUID 和 ROM 已清空，请使用自己生成的机器身份。
3. 用 [OpenCore 1.0.9](https://github.com/acidanthera/OpenCorePkg/releases/tag/1.0.9) 的 ocvalidate 检查完整 EFI，再从外置介质测试。
4. RTX 4060 Laptop 的第三方驱动见 [NullMoth v2.9](https://github.com/nullmoth/nvidia-macos-driver/releases/tag/v2.9)。

配置由 1401 的构建流程生成。OpenCore、kext 和固件驱动请通过生成工具或各自上游取得，依赖适用各自的上游许可证。仓库提供配置与 SSDT，完整 EFI 需重建。
