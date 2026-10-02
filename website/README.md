# Leqana 产品网站

三个可直接部署的静态网页，无构建依赖、JavaScript、Cookie、第三方字体或统计脚本。网站不会连接 Companion Server。联系邮箱：brendonmaddes@gmail.com。

| 页面         | 文件           | App Store Connect 对应用途 |
| ------------ | -------------- | -------------------------- |
| 产品营销介绍 | `index.html`   | Marketing URL              |
| 隐私政策     | `privacy.html` | Privacy Policy URL         |
| 技术支持     | `support.html` | Support URL                |

## 本地预览

在项目根目录运行：

```bash
python3 -m http.server 9147 --bind 127.0.0.1 --directory website
```

打开 `http://127.0.0.1:9147/`。也可直接打开这三个 HTML 文件，它们使用相对资源和页面链接。共享样式为 `assets/styles.css`，标志为 `assets/mark.svg`。

已检查 1280 px 桌面及 375 px 手机布局、导航、邮件模板、常见问题展开、页面内锚点与资源路径。所有页面仅加载同目录资源。

## GitHub Pages 发布

网站由独立的公开仓库 [Leqana-website](https://github.com/greatgithubfish/Leqana-website) 发布，Leqana 应用与服务器源码仓库继续保持私有。公开仓库仅包含网站文件与发布工作流，拥有独立历史，不包含应用源码、数据库、密钥或用户媒体。

公开网址：

- 营销：<https://greatgithubfish.github.io/Leqana-website/>
- 隐私：<https://greatgithubfish.github.io/Leqana-website/privacy.html>
- 支持：<https://greatgithubfish.github.io/Leqana-website/support.html>

更新网页后：

1. 将本目录的变更同步到公开仓库的 `website/`，检查只包含公开网站文件，然后提交并推送到 main。
2. 在公开仓库 Actions 中选择 **Publish Leqana website**，手动运行 main 的工作流。推送代码不会自动发布。
3. 部署成功后，在未登录状态下验证三个页面与样式资源。

工作流 `.github/workflows/website-pages.yml` 只上传 `website/`。主私有仓库保留的同名工作流不用于当前发布；当前 GitHub 套餐不支持从该私有仓库发布 Pages。规则见 [GitHub Pages 官方说明](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages)。

## 内容说明与维护

- 隐私政策按当前 V1 的代码和部署方式撰写，覆盖本地与服务端存储、AI 服务、参考照片与声音样本、APNs 消息预览、权限、删除与备份边界。
- 服务器自托管不等于数据永不离开设备；选择云端 Provider 时相关内容会发送给它。没有作出端到端加密、不训练等未经实现或验证的承诺。
- 产品页的手机和日程是清楚标注的界面示意，没有使用真实用户聊天、照片或截图。没有伪造 App Store 下载地址、收费方案或发行日期。
- 邮件支持入口打开用户的邮件应用并填入反馈模板，网页本身不收集表单，也不自动发送邮件。
- 政策已说明 GitHub Pages 为安全记录访问者 IP，并链接 GitHub 隐私声明。更换托管平台、运营者信息或支持邮箱时，应同步更新本政策。平台行为见 [GitHub 官方说明](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages#data-collection)。
- [Apple 官方文档](https://developer.apple.com/help/app-store-connect/reference/app-information/platform-version-information/)说明 Support URL 需要实际联系方式；[隐私政策要求](https://developer.apple.com/app-store/review/guidelines/#privacy)覆盖数据使用、第三方、保留和删除。本网页不代表 App Store 审核通过，也没有替应用填写隐私标签；正式版本的数据声明还需与实际收集方式一致。
- 获得正式 App Store 链接后，可替换产品页开始使用入口；改动数据流或增加统计服务时同步更新政策和日期。
