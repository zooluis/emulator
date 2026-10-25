# Citron Neo

<img src="./dist/citron.svg" width="128" alt="Citron Neo logo">

Citron Neo 是一個開源模擬器，延續了 Citron 程式碼庫。它可以在 Windows、Linux、macOS 和 Android（arm64）上執行。開發與維護在 [Discord](https://discord.gg/7bdSQgQZfu) 上進行。

## 建置

程式庫相依項目在設定時由 CPM 取得，所以無需先初始化子模組。

**Linux。** 先執行 `./build-citron-linux.sh setup` 一次，再執行 `./build-citron-linux.sh use --pgo none --lto full` 進行不帶效能分析輪次的建置。二進位檔生成在 `build/use-nopgo/bin/citron`，旁邊還有 AppImage。[docs/BUILDING-CITRON-LINUX.md](docs/BUILDING-CITRON-LINUX.md) 介紹了 PGO 各階段，可帶來最佳效能。

**Windows。** 用 clang-cl 原生建置，或用 llvm-mingw 從 Linux 交叉編譯。[docs/BUILDING-CITRON-WINDOWS.md](docs/BUILDING-CITRON-WINDOWS.md) 同時涵蓋兩者。

**Android。** 從 `src/android` 執行 `./gradlew assembleMainlineRelease`。如果環境裡沒有發布用的 keystore，APK 會使用隨附的除錯金鑰簽章。

## 貢獻

歡迎提交 issue 和 PR。開始大工程前先在 Discord 上詢問。回報 bug 時，請說明你用的平台、GPU 和驅動，以及你執行的 commit 或建置版本。

## 授權條款

GPL-3.0-or-later。見 [LICENSE](LICENSE)。第三方元件及其授權條款在 [LICENSES/](LICENSES/) 中。
