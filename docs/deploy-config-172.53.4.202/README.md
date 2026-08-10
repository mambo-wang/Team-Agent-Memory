# 172.53.4.202 部署配置文件归档

本目录归档了 TDAI 三件套（memory-core / memory-hub / proxy）部署在 172.53.4.202 时的关键配置文件，供排查与重建参考。

## 文件清单

| 文件 | 对应服务器路径 | 说明 |
|------|----------------|------|
| `global-images.env` | `/opt/memorycore/global-images/.env` | 部署环境变量（三件套镜像、端口、上游 LLM、embedding） |
| `tdai-gateway.yaml` | `/opt/memorycore/tdai-gateway.yaml` | TDAI Gateway standalone 网关配置 |
| `proxy-config.yaml` | `/opt/memorycore/global-images/.proxy-config/config.yaml` | Proxy 运行配置（由 start-proxy.sh 启动时自动生成） |
| `memory-core-config.yaml` | `/opt/memorycore/global-images/.memory-core-config/tdai-gateway.yaml` | memory-core 网关配置（由 start-memory-core.sh 启动时自动生成） |

## 安全说明

- 所有 API Key 已替换为 `<REDACTED>` 占位符，**禁止**将真实密钥提交到 git 仓库。
- `proxy-config.yaml` 与 `memory-core-config.yaml` 带"由脚本自动生成，启动时覆盖"的注释，手动修改不生效，需改 `.env` 后重启。
