# 刘欣越 · 空间与数字之间

刘欣越的个人作品网站，展示建筑、规划、CIM 与遗产保护研究。使用 HTML、CSS、JavaScript 和 SVG，无需安装前端依赖或构建。

网站通过本仓库的 GitHub Pages 发布，实际地址见仓库 About 或 Settings → Pages。

## 页面与互动

- About Me：恢复第一次上传 2D 头像后的棕色侧分长发、圆框眼镜、奶油脸与绣球花瓣。眼睛跟随指针，点击时眯眼歪头；泰迪保留吐舌头互动。政治面貌、软件技能、兴趣爱好排列在右侧自我介绍末句“交互体验。”之后。
- The Journey：学习经历、工作经历并列展示，保留实习身份说明。
- Selected Experience：建筑、规划、CIM、遗产保护四个模块。首屏浮标直接跳转到相应模块。
- 遗产保护按古舆图手势交互、明代海防建置地图、海防遗产数字图志排列。
- 原始作品阅读器支持章节、翻页、缩放与 PDF 下载。
- 联系方式支持独立复制邮箱与手机号。
- 支持键盘操作、移动端布局和减少动画偏好。人物按钮聚焦后，方向键改变视线，Esc 恢复；Enter 或空格触发互动。

## 文件结构

网站文件直接位于仓库根目录。

| 路径（相对于网站根目录） | 用途 |
| --- | --- |
| `index.html` | 页面内容、模块顺序与内联头像 |
| `style.css` | 字体、留白、响应式布局与动画 |
| `app.js` | 作品阅读器、遗产切换、人物与浮标互动 |
| `assets/character/xinyue-robot.svg` | 可复用的分层头像源文件 |
| `assets/architecture/` | 建筑作品集与页面预览 |
| `assets/planning/` | 芦蒲村规划作品集与页面预览 |
| `assets/amsterdam/` | CIM 原始展板与 PDF |
| `assets/heritage/` | 舆图、点位示意图 |
| `experiences/` | 已有遗产交互项目的本地展示版本与数据 |

## 本地查看

在仓库根目录执行：

```sh
python3 -m http.server 8000
```

打开 `http://localhost:8000`。

## 自动部署

修改网站文件后提交到 `main`，GitHub Actions 会自动发布到 GitHub Pages。部署配置位于 `.github/workflows/deploy.yml`，无需安装前端依赖。

在仓库 **Settings → Pages** 中选择 **GitHub Actions** 作为发布来源。可在 **Actions** 中查看部署结果。

## 编辑说明

修改人物 SVG 后，需要同时更新 `index.html` 内的头像。两只眼睛共同使用 `.robot-gaze` 和 `.robot-blink`，避免只移动一只眼睛。视线中心和移动范围由头像 SVG 的 data-gaze 属性定义。

修改个人内容时，先编辑 `index.html`；作品详情与遗产切换内容位于 `app.js` 的 `projects`、`portfolios`、`researchViews`。页面路径使用相对地址，可部署在 GitHub 项目子目录。

英文字体优先 Calibri，中文优先幼圆；本仓库不分发商业字体文件，未安装对应字体的设备使用后备字体。

## 来源与许可

原创网站界面代码（`index.html`、`style.css`、`app.js` 与导出脚本）采用 MIT 许可证，见 `LICENSE`。许可证仅覆盖代码，不授权使用刘欣越的姓名、头像、联系方式、个人简历、作品集 PDF、作品图像、研究数据或第三方素材；这些内容不纳入 MIT 授权范围，引用或再利用需取得相应权利人的许可。

遗产展示基于既有项目 https://github.com/Yueee-0305/zhedong_Yutu ，保留其资料与引用说明。`experiences/` 内第三方组件保留原有许可证。遗产名录统计含历时记录、候选点位，不能等同于某一时点真实遗址总数；原始作品中的参考资料以 PDF 为准。

## 验证范围

已检查 HTML 结构、站内资源、锚点、SVG 与 JavaScript 语法，以及人物交互状态与指针范围。当前环境未执行整页浏览器视觉验收。嵌入地图底图依赖联网，完整手势体验在原项目中运行。

## 版本说明

本版本为本人审核确认后的个人网站，包含建筑、规划、CIM、遗产保护四个作品模块。
