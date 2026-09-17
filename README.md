# FITS Studio Extensions

FITS QuickLook Studio 的公开扩展目录。这里只存放 App 介绍和商店链接，不托管 App 程序或主软件源码。

## 添加一个扩展

1. 将独立 macOS App 发布到 App Store，取得数字 Apple ID。
2. 编辑 `extensions.json`，在 `extensions` 数组中新增条目。
3. 填入唯一的 `id`、App 名称 `name`、实际 `bundleIdentifier`、数字 `appStoreID`、多语言 `summaries` 和兼容 `formats`。
4. 提交到 `main` 分支。主软件打开“发现扩展”后自动更新目录，也可点击“刷新”。网络/CDN 缓存可能使更新稍有延迟。
5. 用户在 App Store 安装后，回到主软件，“已安装”中会显示该 App。

不是上传 `.app` 文件，也不是上传一个新名字就能增加主软件的内部功能。

## 文件包协议

支持的 `formats`：

- `{"kind":"appearance","version":1}`：兼容 `.fitsappearance` 外观包。
- `{"kind":"chromara","version":1}`：兼容 `.chromara` 配色包。
- `{"kind":"astronote","version":1}`：兼容 `.astronote` 标注包。
- 独立工作、无需文件包导入的 App 可使用 `[]`。

新 App 必须真实输出对应格式并满足主软件的校验规则。新的不兼容格式、算法或主软件界面仍需要主软件适配。不要修改已有条目的身份字段或协议版本。

`summaries` 支持 `zh-Hans`、`en`、`fr`、`es`、`de`，英文必填。目录 `schemaVersion` 保持为 1。

## 更新行为

- 兼容此目录的主软件会在打开扩展页、回到前台时检查目录，自动检查间隔至少一小时；手动刷新可立即检查。
- 安装状态在本机按 Bundle ID 检测。
- 网络不可用时使用最近一次有效缓存；缓存不可用时使用三个内置条目。
- 主软件只读取目录数据，不下载或执行远程代码。

Raw URL: https://raw.githubusercontent.com/hudongsheng-debug/FITS-Studio-Extensions/main/extensions.json


## Pending releases and FrameScout

New Studio builds read `extensions-v2.json`. An empty `appStoreID` means Coming Soon: installed apps can open, but the store button is disabled. Replace the empty value with the real numeric Apple ID when released. `extensions.json` remains the legacy feed; add released entries there too for older clients. FrameScout exports ordinary FITS files, so `formats` is empty; users open those FITS through Studio’s normal file opening workflow. CSV reports are not imported as extension packages.
