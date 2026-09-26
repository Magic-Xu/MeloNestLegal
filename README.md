# MeloNest 官网与法律页面

本仓库是产品首页、隐私政策和用户协议的唯一维护源。直接修改这里的 HTML；样式和 App 内浏览的 `#app-view` 适配保留在对应页面中。

- 官网：https://magic-xu.github.io/MeloNestLegal/
- 根目录为英文页面，`en/`、`zh-CN/` 为现有语言入口；保持公开路径和 App 链接稳定。
- 文案先核对 App 的真实功能、SDK、权限和数据处理，再更新各语言及生效日期。

## 检查与预览

```sh
python3 tools/validate_site.py
python3 -m http.server 8000 --bind 127.0.0.1
```

`site.json` 记录发布根地址和必需页面。检查器只读校验页面、内部链接和传入的 App URL 锚点，不代替正文审查。
App 仓库的 `tools/release/validate_legal_site.py` 调用本仓库检查器，核验全部 Android 语言资源中的法律链接。

## 发布

在本仓库的功能分支修改并提交。PR 检查通过、页面审查完成且已获发布授权后，合入 `main`；Pages 工作流再次校验后部署。
部署完成后核对线上中英文页面、隐私说明、生效日期及 `#app-view` 模式。App 仓库的提交不会发布网站。
