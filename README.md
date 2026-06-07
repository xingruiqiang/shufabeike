# 翰墨碑林 · 书法碑刻鉴赏研学网站

> 观碑摹帖 · 心摹手追

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![CSS3](https://img.shields.io/badge/CSS3-1572B6?logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![GitHub Pages](https://img.shields.io/badge/Deploy-GitHub%20Pages-blue?logo=github)](https://pages.github.com)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](CONTRIBUTING.md)

**翰墨碑林**是一个为书法爱好者打造的纯静态鉴赏研学网站。无需后端、开箱即用，双手收下历代名碑法帖的高清图像、毛笔技法精要与千年书坛轶事，在宣纸般的古雅氛围里，与古贤神交。

如果你是书法爱好者、临摹学习者，或只是想沉浸在汉字之美中，这里就是你的书斋。

[在线预览](#在线预览) · [功能一览](#功能一览) · [快速使用](#快速使用) · [碑帖收录](#碑帖收录) · [部署指南](#部署指南) · [贡献碑帖](#贡献碑帖)

---

## 在线预览

直接用浏览器打开 `index.html`，无需任何服务器或安装步骤。

```bash
# 克隆仓库
git clone https://github.com/your-username/hanmo-beilin.git
cd hanmo-beilin

# 直接用浏览器打开（Windows）
start index.html

# macOS
open index.html

# 或部署到任意静态服务器（GitHub Pages / Vercel / Nginx）
```

---

## 功能一览

### 🏛️ 碑刻画廊 · 临池宝鉴
以卡片网格呈现七件经典碑帖，每张卡片包含碑帖缩略图、名称、年代作者与风格点评。点击任意卡片，**全屏模态框**放大高清图像，细观笔意墨韵，按 `Esc` 或点击背景即可退出。

### 🖌️ 笔法精要 · 技法心传
四大书法技巧专栏：**执笔之法**、**中锋用笔**、**临摹要诀**、**墨法润燥**，结合兰亭序、乙瑛碑等具体碑帖举例，专业而实用。

### 📜 翰墨遗珍 · 轶事品藻
左右双栏设计：
- **书坛趣闻**：王羲之写经换鹅、赵孟頫日书万字、颜真卿悲愤挥毫等经典轶事
- **名贤品评**：何绍基、黄庭坚、董其昌、康有为等历代大家的评语引用，注明原始出处

### 📌 其他亮点
- 顶部固定导航，平滑滚动至对应区块
- 图片**懒加载**（`loading="lazy"`），首屏极速
- 图片加载失败时自动显示**精致占位图**，不破坏整体布局
- 全站**响应式**，iPhone SE（375px）至 4K 宽屏均适配

---

## 技术栈

| 层次 | 技术 |
|------|------|
| 结构 | HTML5 语义化标签 |
| 样式 | CSS3 · Flexbox + Grid · 媒体查询 |
| 交互 | 原生 JavaScript（ES6）· 无框架 |
| 字体 | [Noto Serif SC](https://fonts.google.com/nspecimen/Noto+Serif+SC)（Google Fonts） |
| 图标 | [Font Awesome 6](https://fontawesome.com)（Free CDN） |
| 部署 | 任意静态托管平台：GitHub Pages / Vercel / Netlify / Nginx |

> 不依赖任何前端框架，全项目仅一个 `index.html`，便于爱好者自行修改与维护。

---

## 快速使用

### 本地预览

```bash
git clone https://github.com/your-username/hanmo-beilin.git
cd hanmo-beilin
# 直接双击 index.html 或用 Live Server 等插件启动
```

### 替换图片

所有图片存放在 `images/` 目录，按碑帖名分子目录管理：

```
images/
├── lantingxu.jpg          # 王羲之《兰亭序》
├── yiying_bei.jpg         # 汉《乙瑛碑》
├── caoquanbei.jpg         # 汉《曹全碑》
├── dutongtie.jpg          # 张旭《肚痛帖》
├── 洛神赋/                 # 赵孟頫《洛神赋》
├── 祭侄文稿/               # 颜真卿《祭侄文稿》
└── 快雪时晴帖/             # 王羲之《快雪时晴帖》
```

在 `index.html` 的 `steleData` 数组中修改 `thumb` / `large` 字段即可更换任意图片：

```javascript
{
    name: "王羲之《兰亭序》",
    thumb: "images/lantingxu.jpg",   // 卡片缩略图路径
    large: "images/lantingxu.jpg",   // 模态框大图路径（可用不同高清版本）
    ...
}
```

### 增加碑帖

在 `steleData` 数组末尾追加一个对象即可，网格自动扩展：

```javascript
{
    name: "欧阳询《九成宫醴泉铭》",
    desc: "唐·贞观六年 楷书极则",
    brief: "险劲刚健，法度森严，楷书第一",
    thumb: "images/jiuchenggong.jpg",
    large: "images/jiuchenggong.jpg",
    placeholderTitle: "九成宫"
}
```

---

## 碑帖收录

| 碑帖名称 | 年代 · 作者 | 书体 | 历史地位 |
|---------|------------|------|---------|
| 王羲之《兰亭序》 | 东晋 · 永和九年 | 行书 | 天下第一行书 |
| 汉《乙瑛碑》 | 东汉 · 永兴元年 | 隶书 | 汉隶典范，孔庙三碑之首 |
| 赵孟頫《洛神赋》 | 元 · 大德年间 | 行楷 | 结字妍丽，二王嫡脉 |
| 汉《曹全碑》 | 东汉 · 中平二年 | 隶书 | 汉石第一神品（康有为语） |
| 颜真卿《祭侄文稿》 | 唐 · 乾元元年 | 行书 | 天下第二行书 |
| 张旭《肚痛帖》 | 唐 · 年代不详 | 狂草 | 颠张醉素，草圣极致 |
| 王羲之《快雪时晴帖》 | 东晋 | 行书 | 乾隆三希堂之首 |

---

## 部署指南

### GitHub Pages（推荐）

1. Fork 本仓库
2. 进入仓库 **Settings → Pages**
3. Source 选择 `main` 分支，根目录 `/`
4. 保存后稍等片刻，访问 `https://your-username.github.io/hanmo-beilin`

### Vercel

```bash
npm install -g vercel
vercel --prod
```

### Nginx

```nginx
server {
    listen 80;
    server_name your-domain.com;
    root /var/www/hanmo-beilin;
    index index.html;
}
```

---

## 验收标准

- [x] 七件碑帖均可正常展示，点击弹出大图
- [x] 图片加载失败时显示优雅占位图
- [x] `Esc` 键关闭模态框
- [x] 导航锚点平滑滚动
- [x] iPhone SE（375px）至桌面（1920px）布局正常，无横向溢出
- [x] 图片懒加载生效，控制台无报错
- [x] 技法内容专业，史实评语注明出处

---

## 贡献碑帖

欢迎提交 PR，为画廊补充更多经典碑帖或完善文字内容！

**贡献方式：**

1. Fork 本仓库并新建分支
2. 在 `images/` 下新增图片（建议使用 CC 协议或公有领域图片）
3. 在 `steleData` 数组中添加对应数据
4. 提交 PR，描述碑帖来源与授权信息

**注意事项：**
- 图片须为公有领域（PD）或 CC 授权，并在 PR 中注明来源
- 碑帖历史信息请尽量引用可考文献，避免杜撰
- 单张图片建议压缩至 2MB 以内，保证加载体验

---

## 图片来源与版权

本项目所用碑刻拓本图片均来自以下公有领域资源：

- [维基媒体共享资源（Wikimedia Commons）](https://commons.wikimedia.org) — CC BY-SA / 公有领域
- 台北故宫博物院公开影像
- 用户自行收集的公有领域碑拓图像

> 所有碑刻图像仅供研学鉴赏，不作商业用途。

---

## License

[MIT](LICENSE) © 2026 翰墨碑林

---

> 心摹手追，神交古贤 · 沉浸墨海，传承文心 🖌️
