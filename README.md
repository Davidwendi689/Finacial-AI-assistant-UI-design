# Finora AI

Finora AI 是一个中文个人记账与消费分析原型。它自带示例账本，支持一句话生成记账草稿、查找流水、对比预算，以及切换柱形图和折线图查看近六个月支出。

## 快速开始

预览入口是仓库根目录的 [`index.html`](index.html)。GitHub 的文件页显示源码。要体验交互，点击 **Code → Download ZIP** 下载整个项目并解压，然后在解压后的项目根目录启动本地静态服务器。Windows 可以使用 `py`，macOS 和 Linux 可以使用 `python3`。

```powershell
py -m http.server 8000 --bind 127.0.0.1
```

```bash
python3 -m http.server 8000 --bind 127.0.0.1
```

然后打开 <http://127.0.0.1:8000/>。使用近期版本的 Chrome、Edge、Firefox 或 Safari，无需安装前端依赖、构建应用或配置 API 密钥。

在首页输入「晚饭 28，地铁 4」并发送，即可核对两笔草稿。也可以提问「这月餐饮花了多少？」。示例账本以 **2026 年 11 月 13 日**为演示日期。

## 功能

| 页面 | 可以做什么 |
| --- | --- |
| 总览 | 查看本月收支和预算，输入文字生成记账草稿，查看支出趋势 |
| 流水 | 按日期浏览，搜索和筛选记录，编辑或删除单笔流水 |
| 分析 | 查看消费构成、分类排行和预算对比，切换柱形图与折线图 |
| AI 查账 | 在浏览器内按月份、分类和近 30 天规则查询示例或本地账本 |
| 预算 | 为月度总支出和各分类设置限额，查看使用进度 |

## 文件结构

```text
.
├── index.html           # 应用入口与页面骨架
├── assets/
│   ├── css/app.css      # 布局、主题和动画样式
│   ├── js/app.js        # 账本、查询、图表和交互逻辑
│   └── images/          # 背景、贴纸图集和吉祥物
├── ASSETS.md            # 图片来源与公开分发核对
├── SECURITY.md         # 数据边界与问题报告
├── LICENSE             # 代码采用 MIT 许可证
└── .nojekyll            # GitHub Pages 按静态文件发布
```

## 数据与隐私

账本修改保存在当前浏览器的 `localStorage` 中。小票照片只用浏览器的临时图片链接预览，关闭录入窗口后释放该链接。真实图片需要对照填写，示例小票提供模拟预填。账本查询采用本地规则。清除站点数据、换浏览器或更换访问地址会影响读取原账本。

原型以演示账本为主要用途。涉及真实收支和票据信息前，请先评估本地存储、访问权限和备份要求。详见 [SECURITY.md](SECURITY.md)。

## 检查与发布

修改后可运行 `node --check assets/js/app.js` 检查脚本语法。在浏览器中试用一次新增、筛选、预算设置、图表切换和图片预览，再查看开发者工具是否有资源加载或脚本错误。

要通过 GitHub Pages 提供演示，在仓库 **Settings → Pages** 里选择 **Deploy from a branch**，源设为 `main` 和 `/(root)`。部署成功后，用 Pages 显示的地址打开项目并复查图片、样式和交互。图片和授权状态见 [ASSETS.md](ASSETS.md)。[GitHub Pages 发布文档](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)

提交 PR 时，写清改动动机、手动验证步骤和受影响的页面。界面改动附一张使用示例账本的截图。

## 授权

前端代码和项目文档按仓库中的 [MIT 许可证](LICENSE) 分发。第三方标识和图片的再使用或分发条件见 [素材说明](ASSETS.md)。
