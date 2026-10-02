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

已准备 `.github/workflows/website-pages.yml`。**它仅支持手动运行，推送代码不会自动发布网站。** 工作流只上传 `website/`，不上传 iOS、Server 源码、数据库、密钥或媒体。当前还没有启用或运行 Pages 发布。

1. 确认 GitHub 账号支持从私有仓库发布 Pages。在仓库 Settings › Pages 中，Source 选择 GitHub Actions。
2. 在 Actions 中选择 **Publish Leqana website**，点击 **Run workflow**，选择 main。
3. 成功后使用工作流给出的公开 URL 验证三个页面可以在未登录浏览器中访问。

按当前仓库名且未设置自定义域名，默认地址预计为：

- 营销：`https://greatgithubfish.github.io/Leqana/`
- 隐私：`https://greatgithubfish.github.io/Leqana/privacy.html`
- 支持：`https://greatgithubfish.github.io/Leqana/support.html`

**以上是待部署地址，当前不应当作已上线链接或填入审核资料。** GitHub Free 只支持公开仓库的 Pages；私有仓库需要适用的付费计划。若账号不支持，可将 `website/` 单独部署到其他静态托管平台，或在得到授权后使用单独的公开网站仓库，保持本项目私有。规则见 [GitHub Pages 官方说明](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages)。

## 内容说明与维护

- 隐私政策按当前 V1 的代码和部署方式撰写，覆盖本地与服务端存储、AI 服务、参考照片与声音样本、APNs 消息预览、权限、删除与备份边界。
- 服务器自托管不等于数据永不离开设备；选择云端 Provider 时相关内容会发送给它。没有作出端到端加密、不训练等未经实现或验证的承诺。
- 产品页的手机和日程是清楚标注的界面示意，没有使用真实用户聊天、照片或截图。没有伪造 App Store 下载地址、收费方案或发行日期。
- 邮件支持入口打开用户的邮件应用并填入反馈模板，网页本身不收集表单，也不自动发送邮件。
- 发布前确认本政策仍符合实际部署、运营者信息及支持邮箱。部署到 GitHub Pages 后，托管平台会为安全记录访问者 IP；应将 `privacy.html` 网站章节改为说明实际平台并链接其政策。平台行为见 [GitHub 官方说明](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages#data-collection)。
- [Apple 官方文档](https://developer.apple.com/help/app-store-connect/reference/app-information/platform-version-information/)说明 Support URL 需要实际联系方式；[隐私政策要求](https://developer.apple.com/app-store/review/guidelines/#privacy)覆盖数据使用、第三方、保留和删除。本网页不代表 App Store 审核通过，也没有替应用填写隐私标签；正式版本的数据声明还需与实际收集方式一致。
- 获得正式 App Store 链接后，可替换产品页开始使用入口；改动数据流或增加统计服务时同步更新政策和日期。
