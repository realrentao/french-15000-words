# 法语单词随身背 · 互动学习站

《最好用最好记15000法语单词随身背》(帕特里克 / 杨小盼 / 方振宇 / 振宇锐智教学研究中心) 完整版互动学习网站。

**线上地址**：<https://realrentao.github.io/french-15000-words/>
**源码仓库**：<https://github.com/realrentao/french-15000-words>

> 数据来源：原书扫描 PDF → OCR 提取 → 保留 **Chapitre → Partie → Section** 三级结构，以及终极分类词、经典实用句、词汇大拓展三大板块。修复法语特殊字符（`é / è / à / ç / œ` 等）与 OCR 断字问题。

## 功能

### 📖 完整还原原书结构
按 **Chapitre → Partie → Section** 三级层级导航，每个 Section 含三个原书固定板块：

- **终极分类词**：场景核心词表（中/法/词性）
- **经典实用句**：地道法语句 + 中文翻译
- **词汇大拓展**：相关词/搭配拓展

### 🔊 双语音频
- 法语女声 `fr-FR-DeniseNeural`
- 中文女声 `zh-CN-XiaoxiaoNeural`
- 例句、词条、拓展词全部真人发音，**每个词/句独立 mp3 离线播放**

### 🔤 拼音 + 法语音标
- 中文释义标注 **拼音**（pypinyin 生成）
- 法语单词/例句标注 **国际音标**（取自原书方括号音标）
- 顶栏「拼」按钮一键显示/隐藏

### 🎴 学习模式（闪卡 + 测验 + SRS）
顶栏「学」按钮进入：
- **闪卡**：正面法语 + 音标，翻面出中文 + 拼音
- **测验**：给中文释义，四选一法语选项
- **SRS 间隔重复**：10 分钟 / 1 小时 / 1 天 / 3 天 / 7 天
- 进度存 `localStorage`，可导出/导入

### ▶ 全盘播放
底部控制条：
- 范围：本节 / 本大类 / 全书
- 顺序：法→中（逐条）/ 全部法语→全部中文 / 仅法语 / 仅中文
- 语速、间隔、循环
- 双 Audio 交替预载

### 🔍 其他
- 全局搜索（法语/中文）
- 词条点读
- 深色 / 浅色主题
- 移动端响应式
- 键盘快捷键：`空格`播放/暂停，`←` `→`上下条，`/` 聚焦搜索

## 文件结构

```
french-vocab-site/
├── index.html              # 入口
├── css/style.css
├── js/app.js               # 单文件 SPA
├── data/
│   ├── meta.js             # 索引
│   └── sec/*.js            # 分册懒加载
└── audio/
    ├── fr/*.mp3            # 法语音频
    └── zh/*.mp3            # 中文音频
```

## 本地预览

```bash
cd french-vocab-site
python -m http.server 8811
# 浏览器打开 http://127.0.0.1:8811/
```

## 部署

GitHub Pages（`main` 分支根目录）。

```bash
git remote set-url origin ssh://git@ssh.github.com:443/realrentao/french-15000-words.git
git push origin main
```

## 技术栈

零依赖、零构建：原生 HTML / CSS / JavaScript，单文件 SPA。
- 配音：`edge-tts`（Microsoft Azure TTS）
- OCR：`EasyOCR`（法语 + 中文简体）
- 音标：取自原书方括号注音
