# henryinuk.github.io 维护指南（新版主页）

纯静态站点，无构建步骤：改完 index.html 直接 git push 即部署。

## 文件结构
- index.html — 唯一页面，所有内容都在这里
- support.js — 页面渲染运行时，**不要修改**
- assets/img/ — 图片（logo、研究方向图标、头像 avatar-new.jpg）
- assets/files/ — CV PDF

## index.html 结构
- <helmet><style> 内是全局配色变量：浅色在 :root，深色在 @media (prefers-color-scheme:dark)。主题强调色 = --accent。
- <x-dc> 与 </x-dc> 之间是页面内容（HTML，内联样式）。
- 底部 <script data-dc-script> 是少量交互逻辑（中英切换、News 展开），一般不需要动。

## 双语规则（重要）
每处文案成对出现，改内容时两个都要改：
- 行内：<span style="display:var(--en,inline)">English</span><span style="display:var(--zh,none)">中文</span>
- 块级：display:var(--en-b,block) / var(--zh-b,none)
纯英文内容（论文标题、作者、期刊名）不需要成对。

## 常见更新
- 加 News：在 News 区块复制一整行 <div style="display:flex;gap:16px">…（日期 span + 双语正文 span），最新放最上面。默认只显示前 5 条：第 6 条起要包在 <div style="display:var(--news-extra,none)"> 里，并把逻辑脚本与按钮文案里的“全部 10 条 / all 10 entries”数字改成新总数。
- 加论文：复制一个 grid-template-columns:88px 1fr 条目，改 venue 标签、标题、作者（本人加粗）、期刊/会议与年份、[PDF] 链接；会议录用率沿用现有加粗 span 格式（SOCC 不加）。
- 换头像：替换 assets/img/avatar-new.jpg（正方形裁切最佳）。
- 换主题色：同时改 :root 和 dark 里的 --accent。

## 本地预览
python3 -m http.server 然后打开 http://localhost:8000（直接双击 index.html 也可，字体加载需联网）。
检查项：中英切换、News 展开/收起、深浅色（跟随系统）、图片与 CV 链接。
