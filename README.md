# AICom 插件市场

AICom「插件市场」功能的数据源仓库。AICom 客户端拉取 `market.json` 索引，展示可安装插件，一键下载 release zip 资产并热安装。

## 发布新插件 / 新版本

1. 准备插件包目录（根目录含 `manifest.json`，运行环境自包含）
2. 清理开发产物（日志、`__pycache__`、本机配置），压缩为 `<name>-<version>.zip`
3. 创建 release：tag = `<name>-<version>`，上传 zip 为 asset
4. 更新 `market.json`（version/asset URL/sizeMB）并提交

## 索引格式

```json
{
  "plugins": [
    {
      "name": "flasher",
      "title": "RDA 固件烧录",
      "version": "1.0.0",
      "group": "烧录",
      "description": "...",
      "asset": "https://github.com/.../download/flasher-1.0.0/flasher-1.0.0.zip",
      "sizeMB": 34.4
    }
  ]
}
```
