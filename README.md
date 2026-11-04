# tapd-helper-release

本仓库**只存放发布产物**，不含源码。源码不在此仓库，也不在本仓库的提交历史里。

## 内容

| 文件 | 说明 |
| --- | --- |
| `tapd-helper.exe` | Windows 托盘程序（PyInstaller 单文件，约 22MB） |
| `update.json` | 自更新清单：`version` / `download_url` / `sha256` / `notes` |

## 客户端怎么用

检查更新时请求：

```
https://github.com/loopsteam/tapd-helper-release/releases/latest/download/update.json
```

版本号通过白名单、`sha256` 校验通过后，才会下载并替换 `tapd-helper.exe`。

## 怎么发布

本机的 `scripts/github_release_publisher.py` 完成全部步骤：构建前端 → 跑测试 →
PyInstaller 打包 → 上传本仓库 Release → 写 `update.json`。没有 CI。
