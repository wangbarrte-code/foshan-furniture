# 佛山源头全屋家居 · 独立站

## 线上地址
https://wangbarrte-code.github.io/foshan-furniture/

## 仓库
https://github.com/wangbarrte-code/foshan-furniture （GitHub Pages，main 分支根目录）

## 站点内容
- `index.html` 首页（双语 EN/中文，WhatsApp 询盘 +86 17724786973）
- `products.html` 产品页（读 `products.json` 渲染，分类 tab + 分页）
- `products.json` 产品数据：**10 分类 / 234 条**，每条图片路径均经校验存在
- `images/` 产品图 234 张，长边 1600px JPEG q82，共 41MB
- `images/_cards/` 首页卡片专用图（从图册页裁出的纯净产品区，9 张）
- `.nojekyll` **必需** —— 否则 GitHub Pages 的 Jekyll 会忽略 `_cards/` 等下划线目录

## 更新流程
```bash
cd ~/Desktop/全屋家居独立站
git add -A && git commit -m "更新说明"
git -c http.version=HTTP/1.1 push origin main   # Pages 约 1 分钟自动重建
```
推送后验证：浏览器打开线上地址（curl 会被 CDN 缓存，不可靠）。

## 本地保留（未入库）
| 位置 | 内容 |
|------|------|
| `~/Desktop/全屋家居独立站_高清原图/` | 3840×3840 原始图 897MB（压缩前，做印刷/大图用） |
| `~/Desktop/全屋家居独立站_备份_20260916_1213.tar.gz` | 整理前的原始站点快照 |
| `全屋家居产品图/` | 12 个源 PDF 图册（510MB，未入库） |
| `server.js` / `admin.html` / `package.json` | 本地后台（上传/删图用，未入库） |
| `rebuild_products.py` | 扫 images/ 重建 products.json |
| `optimize_images.py` | 图片压缩（1600px JPEG q82） |

## 素材已知问题
来源 PDF 图册导出的图里，约 7 个分类（bed / side_table / dining_chair / entry_table 等）是**图册说明页整页截图**，
带 `Factory Outlet` 标题、Description / Material / Dimensions 文字排版，不适合作电商产品图。
首页 10 张分类卡已逐张裁出纯净产品区（`images/_cards/`）；**产品页 234 张仍是原图**（每张布局不同，无法批量裁）。
后续要提升，需从 PDF 重新导出干净单品图，或逐张裁剪。
