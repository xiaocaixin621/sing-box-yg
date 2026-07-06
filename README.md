### Sing-box-yg 优化版一键三协议脚本（VPS 专用）

基于 [yonggekkk/sing-box-yg](https://github.com/yonggekkk/sing-box-yg) 精简优化，保留核心功能，配置变更改用 `jq` 处理，更稳定可靠。

- 支持三大核心协议：**Vless-reality-vision**、**Hysteria-2**、**Tuic-v5**
- 默认 Vless Reality SNI 伪装域名：**www.microsoft.com**
- 支持纯 IPv6、纯 IPv4、双栈 VPS，支持 amd 与 arm 架构，支持 alpine 系统
- 小白简单模式：无需域名证书，回车三次即可安装完成
- 保留 **1.10.7 内核切换**选项，可按需切换 geosite 分流与 IP 优先级功能

---

### 一键安装

SSH 连接服务器后，以 root 执行以下任一命令：

```bash
bash <(curl -Ls https://raw.githubusercontent.com/xiaocaixin621/sing-box-yg/main/sb.sh)
```

或者

```bash
bash <(wget -qO- https://raw.githubusercontent.com/xiaocaixin621/sing-box-yg/main/sb.sh)
```

安装完成后，快捷命令为 `sb`，再次运行即可进入管理菜单。

---

### 优化说明

| 项目 | 说明 |
|------|------|
| 配置变更 | 端口、证书、域名等修改改用 `jq` 解析 JSON，替代按行号 `sed` 替换 |
| 网络调优 | 安装时自动应用 BBR 等 sysctl 调优 |
| 代码精简 | 移除 serv00、workers 等非 VPS 核心组件，聚焦一键部署 |

---

### 项目结构

```
sing-box-yg/
├── sb.sh           # 主脚本（一键安装入口）
├── version         # 版本信息
├── sbwpph_amd64    # WARP-plus-Socks5 二进制 (amd64)
├── sbwpph_arm64    # WARP-plus-Socks5 二进制 (arm64)
└── README.md
```

---

### 致谢

原项目作者：[甬哥 yonggekkk](https://github.com/yonggekkk/sing-box-yg)