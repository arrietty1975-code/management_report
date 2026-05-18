# 经管会报告整理工具 / Management Report Chart Tool

分月录入经管会指标（去年 / 当年 / 环比 / 同比），一键生成双轴柱状 + 折线图，样式对齐经管会标准图表。

## 在线使用（GitHub Pages）

1. 将本仓库推送到 GitHub
2. 打开 **Settings → Pages → Build and deployment**
3. Source 选择 **Deploy from a branch**，Branch 选 `main`，目录选 **`/ (root)`**
4. 保存后访问：`https://<username>.github.io/<repo-name>/`

## 本地使用

需通过 HTTP 访问（浏览器安全策略下 `fetch` 无法读取本地 JSON）：

```bash
# Python 3
cd ai-report-tool
python3 -m http.server 8080
# 浏览器打开 http://localhost:8080
```

## 目录结构

```
ai-report-tool/
├── index.html                      # 主页面（GitHub Pages 入口）
├── data/
│   └── sample-data.json            # 示例分月数据
├── assets/
│   ├── chart-style-reference.png   # 图表样式参考图
│   └── sample-input-template.xlsx  # Excel 导入模板
├── docs/                           # 预留文档目录
├── README.md
└── .gitignore
```

## 功能说明

- **数据录入**：支持增删行、增删指标列；填写去年 / 当年后自动计算环比、同比
- **导入 Excel**：表头格式与 `assets/sample-input-template.xlsx` 一致
- **生成图表**：双轴图（柱：去年/当年，线：环比/同比），可导出 PNG

## 文件命名对照（旧 → 新）

| 原文件名 | 新路径 |
|---------|--------|
| 经管会报告整理工具.html | `index.html` |
| sample-data.json | `data/sample-data.json` |
| 图表样式.png | `assets/chart-style-reference.png` |
| 260518-分月环比ai画图.xlsx | `assets/sample-input-template.xlsx` |

## 技术栈

- 纯静态 HTML + [ECharts](https://echarts.apache.org/) + [SheetJS](https://sheetjs.com/)
- 无构建步骤，可直接托管于 GitHub Pages
