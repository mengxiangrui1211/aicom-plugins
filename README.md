# AICom 插件市场

AICom「插件市场」功能的数据源仓库。AICom 客户端拉取 `market.json` 索引，展示可安装插件，一键下载 release zip 资产并热安装。

> 本仓库为私有仓库：AICom 端需在「插件市场 → 设置 Token」配置有读权限的 GitHub Token。

## 发布新插件 / 新版本

1. 准备插件包目录（根目录含 `manifest.json`，运行环境自包含）
2. 清理开发产物（日志、`__pycache__`、本机配置），压缩为 `<name>-<version>.zip`
3. 创建 release：tag = `<name>-<version>`，上传 zip 为 asset
4. 更新 `market.json`（name/version/asset URL/sizeMB）并提交
5. 设备机端 AICom「插件市场」点「刷新」即可看到新版本，一键更新

> 注意：`name` 是插件唯一 ID（决定端点 `/mcp/<name>` 与本地匹配），一经发布不要轻易改名；
> manifest 内 `AICOM_AGENT_ENDPOINT` 等引用必须与 name 一致。

## 索引格式

```json
{
  "plugins": [
    {
      "name": "RDA-8909B-flasher",
      "title": "RDA 固件烧录",
      "version": "1.0.0",
      "group": "烧录",
      "description": "...",
      "asset": "https://github.com/mengxiangrui1211/aicom-plugins/releases/download/RDA-8909B-flasher-1.0.0/RDA-8909B-flasher-1.0.0.zip",
      "sizeMB": 26.2
    }
  ]
}
```