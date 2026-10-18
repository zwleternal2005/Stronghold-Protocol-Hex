# Stronghold-Protocol-Hex · 更新源

《卫戍协议：盟约》**海克斯模组**的自动更新分发仓库。

> 本仓库**不是游戏本体**。游戏本体与其素材（约 718MB）不在此处，请从作者发布的整包获取。

## 这里有什么

```
update/
  manifest.json        # 版本清单（含每个文件的 SHA-256，Ed25519 签名）
  manifest.json.sig    # 清单签名
  packs/
    hexmod-update-<version>.tar.gz   # 只含与上一版不同的文件
```

客户端（模组内置的更新器）按以下顺序取清单，第一个成功即用：

1. `https://ghfast.top/https://raw.githubusercontent.com/Zwleternal2005/Stronghold-Protocol-Hex/main/update/manifest.json`
2. `https://gh-proxy.com/https://raw.githubusercontent.com/…`
3. 直连 `raw.githubusercontent.com`

拿到清单后校验签名与每个文件的 SHA-256，全部通过才落盘；失败自动回滚到旧版本。

## 安全说明

- 更新包由**离线私钥**签名，公钥内置在客户端。任何人都可以阅读本仓库内容，但**无法伪造一次更新**——
  镜像站即使被替换文件，客户端也会因哈希/签名不匹配而拒绝安装。
- 签名私钥不在本仓库，也不在任何公开位置。
- 更新范围仅限代码 / 数据 / 界面；不改动玩家存档（`var/`）、`node_modules/`、`workshop/`。

## 更新失败怎么办

所有源都不可用时，请从夸克网盘下载整包，或加入反馈群：**189434216**。

## 许可

本模组基于 [Stronghold-Protocol](https://github.com/sganggs/Stronghold-Protocol)（GPL-3.0-or-later）开发，
依 **GNU General Public License v3.0** 发布。原始版权归上游作者所有。
