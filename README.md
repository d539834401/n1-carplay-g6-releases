# N1 CarPlay — 公开下载

用于斐讯 N1 / 2026 款小鹏 G6 / 车机 5.10 / 原车 Carlink 的实验版本分发仓库。

**尚未在目标设备和车辆上验证。** 60 fps、实际延迟、冷启动、自动进入 Carlink 和头枕音频行为均待实车验收。请先在备用启动介质上测试。

[下载最新版本](https://github.com/d539834401/n1-carplay-g6-releases/releases/latest)

每个 Release 提供安装器、ARM64 版本包、对应源码、安装说明、验证记录、网络/日志说明和签名元数据。开发 Git 仓库保持私有；公开安装包内也包含对应源码。完整构建源代码、依赖锁文件、上游版本及许可证见每版的 source.tar.gz。

## 更新

默认公开下载，无需 GitHub Token。GitHub 直连失败后尝试可配置的代理（默认 ghfast.top），随后验证 Ed25519 签名和 SHA-256。代理可达性需以设备实际网络为准，不能保证所有大陆网络长期可用。

```sh
sudo n1-carplayctl configure-update https://github.com/d539834401/n1-carplay-g6-releases/releases/latest/download/latest.json --mirror https://ghfast.top/
sudo n1-carplayctl update --check
# 停车后主动更新
sudo n1-carplayctl update
```

首次使用需在 N1 的 ARM64 Debian/Armbian 上安装 Release 安装器；它不刷写 eMMC、内核或设备树。需自行提供配件认证身份并首次配对 iPhone 与车机。升级检查不会自动安装；错误签名、摘要不符或新服务无法就绪时保留/恢复原版。详细边界见 Release 附件。

运行日志默认持久化，7 天/64 MiB 预算；升级审计约 8 MiB 自动轮转；版本清理保留当前和上一稳定版本。日志名称空间与维护定时器需要安装器落地。

## 来源与许可证

Powered by [OpenXPlay](https://github.com/OpenXPlay/OpenXPlay-Relay)，参考 [DashPlay](https://github.com/yizhixiaoheigou/DashPlay) 的 N1 适配与下载代理方案。保留 AGPL/GPL 及上游署名，见 LICENSE、NOTICE.md 和对应源码内的各组件许可证。

发布包不包含发布私钥、设备 GitHub Token、个人网络/配对数据或配件认证身份。
