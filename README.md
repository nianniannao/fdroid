# fdroid — WM65 Launcher nubia 的 F-Droid 自建源

本仓库是 [WM65-Launcher-nubia](https://github.com/nianniannao/WM65-Launcher-nubia) 的
F-Droid 仓库（自定义源），通过 GitHub Pages 提供索引与 APK。

- 仓库地址：`https://nianniannao.github.io/fdroid/repo`
- 目录页：https://nianniannao.github.io/fdroid/
- 签名指纹（SHA-256）：
  `B4:B3:E4:E9:0C:D6:EF:18:2D:6D:B6:D6:6E:EB:B8:7E:42:7C:E6:7F:7E:B4:8A:2D:1C:19:F8:C4:B7:56:63:5E`

## 结构

```text
repo/                  fdroid 仓库根目录（索引 + APK + 图标）
repo/index-v1.jar      v1 索引（JAR 签名）
repo/index-v2.json      v2 索引
repo/entry.jar          v2 索引签名入口
repo/*.apk             分发的安装包
index.html             仓库说明与安装指引
```

## 更新流程

1. 在 `WM65-Launcher-nubia` 仓库发布新 APK
2. 用 fdroidserver 重新 `update`（见主仓库 `scripts/build_fdroid_repo.sh`）
3. 把新的 `repo/` 覆盖到本仓库并推送
4. Pages 会自动重新发布（约 1 分钟）

> 说明：本源不是 f-droid.org 官方主源。官方主源只收录完全自由软件、且能从源码构建的应用；
> 本项目是基于第三方桌面的 APK 改造与重打包，不满足其收录条件，因此以自建源的方​式分发。
