# Citron Neo

<img src="./dist/citron.svg" width="128" alt="Citron Neo logo">

Citron Neo 是一个开源模拟器，延续了 Citron 代码库。它可以在 Windows、Linux、macOS 和 Android（arm64）上运行。开发与维护在 [Discord](https://discord.gg/7bdSQgQZfu) 上进行。

## 构建

库依赖在配置时由 CPM 获取，所以无需先初始化子模块。

**Linux。** 先运行 `./build-citron-linux.sh setup` 一次，再运行 `./build-citron-linux.sh use --pgo none --lto full` 进行不带性能分析轮次的构建。二进制文件生成在 `build/use-nopgo/bin/citron`，旁边还有 AppImage。[docs/BUILDING-CITRON-LINUX.md](docs/BUILDING-CITRON-LINUX.md) 介绍了 PGO 各阶段，可带来最佳性能。

**Windows。** 用 clang-cl 原生构建，或用 llvm-mingw 从 Linux 交叉编译。[docs/BUILDING-CITRON-WINDOWS.md](docs/BUILDING-CITRON-WINDOWS.md) 同时覆盖两者。

**Android。** 从 `src/android` 运行 `./gradlew assembleMainlineRelease`。如果环境里没有发布用的 keystore，APK 会使用随附的调试密钥签名。

## 贡献

欢迎提交 issue 和 PR。开始大工程前先在 Discord 上询问。报告 bug 时，请说明你用的平台、GPU 和驱动，以及你运行的 commit 或构建版本。

## 许可证

GPL-3.0-or-later。见 [LICENSE](LICENSE)。第三方组件及其许可证在 [LICENSES/](LICENSES/) 中。
