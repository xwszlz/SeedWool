# SeedWool 网站上传包 — 部署检查清单（Vercel 优先，已充分吸收原始预览页内容）

## 包内文件清单

| 路径 | 说明 | 状态 |
|------|------|------|
| `index.html` | 英文预览页（seedwool.com，已重新生成 v2，充分吸收原始预览页内容） | ✅ 已更新 |
| `cn.html` | 中文预览页（seedwool.cn，已重新生成 v2，充分吸收原始预览页内容） | ✅ 已更新 |
| `assets/images/育苗块.jpg` | 产品卡：育苗块 | ✅ 真实图片 |
| `assets/images/种植垫.jpg` | 产品卡：种植垫 | ✅ 真实图片 |
| `assets/images/水稻.jpg` | Hero 主视觉 | ✅ 真实图片 |
| `assets/images/水稻育秧体系.jpg` | 产品卡：水稻育秧体系 | ✅ 真实图片 |
| `assets/images/多孔纤维棉.jpg` | 产品卡：多孔纤维棉 | ✅ 真实图片 |
| `assets/images/营业执照.png` | 证书：营业执照 | ✅ 本地图片 |
| `assets/images/省级科技成果证书.jpg` | 证书：省级科技成果证书 | ✅ 本地图片 |
| `assets/images/国家级科技成果登记证书.jpg` | 证书：国家级科技成果登记证书 | ✅ 本地图片 |
| `assets/images/alibaba_1601651822158.jpg` | 阿里商品卡图（新增，岩棉育苗块） | ✅ 新下载 |
| `assets/images/alibaba_1601651827163.jpg` | 阿里商品卡图（新增，岩棉育苗块） | ✅ 新下载 |

## 已充分吸收原始预览页内容（SeedWool_站点预览首页.html）

### 内容区块映射

| 原始预览页区块 | 新版对应位置 | 处理方式 |
|--------------|------------|---------|
| Hero：SeedWool 品牌标题、三位一体价值主张 | Hero 区块 | 融合原始文案：三位一体、干重 +26.38%、SOD +97.42%、增产 8.2% |
| 三大核心能力：产品制造/标准制定者/数据平台 | 三大核心能力区块 | 完整保留原始三个能力卡片描述 |
| 产品中心：育苗块/种植垫/水稻育秧体系/多孔纤维棉 | 产品中心区块 | 4 个产品卡，带真实图片路径，参数描述完整保留 |
| 阿里巴巴商铺热卖产品 | 阿里国际站区块 | 3 个商品卡 + 底部入口按钮，链向 hbshengding.en.alibaba.com |
| 标准与证书：标准路径、省级/国家级证书、营业执照 | 标准与证书区块 | 3 张证书图片 + 标准路径文案完整保留 |
| 数据看板：干重对比、SOD 对比、区域增产、达标率 | 数据看板区块 | 4 个图表数据 + 4 个徽章完整保留 |
| 合作伙伴：4 个机构 Logo 模板 | 合作伙伴区块 | 4 个机构 Logo 位置 + onerror 回退 |
| CTA：联系方式、留资询盘 | CTA 区块 | 电话 14730578560 / 0318-7807560，地址完整保留 |
| 批次验真弹窗 | 批次验真 Modal | 完整交互组件保留 |
| 符合性判定演示 | 符合性判定区块 | 7 项指标输入 + A/B/C 判定逻辑完整保留 |

## 已完成的合规修改（基于 Hermes 战略规划）

### 1. 品牌合规（裁定 24/30）
- `SeedWool®` → `SeedWool™`（CNIPA 商标未注册前，公开页仅用 `™`，无需注册即可合法使用）
- 中文双锚：「SeedWool™ 无机纤维基质棉」，禁裸出公共品类词「基质棉」

### 2. 公开域零价格（裁定 14）
- 所有产品价格字段改为 `Quote only — never listed`（英文）/ `询价制·公开域不展示单价`（中文）
- 统计栏移除夸大产能/投资数字（原 `8.6B CNY Invested` / `8.6亿` 已移除）
- 公开页无任何价格、毛利、ROI 数值

### 3. 阿里国际站实时嵌入（G21）
- en/cn 双页均嵌入 `https://hbshengding.en.alibaba.com/` iframe（高度 600px）
- 底部附“Enter Alibaba.com International Store →”按钮
- 水稻育秧垫 58×28cm 走 RFQ 询价链（不在架，走 Chat Now / Contact Supplier）

### 4. 阿里商品内容补充
- 16 款农业岩棉产品数据已嵌入 JS（来自 Alibaba 导出，含新下载的 2 张商品图片）
- 商品卡图本地存储于 `assets/images/`，禁热链 alicdn（防盗链）

## 目录层级（上传时必须保持）

```
你的网站根目录/
├─ index.html          （英文首页，Vercel 默认首页）
├─ cn.html             （中文首页）
└─ assets/
    └─ images/
        ├─ 育苗块.jpg
        ├─ 种植垫.jpg
        ├─ 水稻.jpg
        ├─ 水稻育秧体系.jpg
        ├─ 多孔纤维棉.jpg
        ├─ 营业执照.png
        ├─ 省级科技成果证书.jpg
        ├─ 国家级科技成果登记证书.jpg
        ├─ alibaba_1601651822158.jpg
        └─ alibaba_1601651827163.jpg
```

**不要**只上传 HTML 而漏掉 `assets/` 文件夹，**不要**修改图片文件名。

## Vercel 部署步骤（推荐，海外免备案）

### 步骤 1：准备部署包
将 `SeedWool_网站上传包` 下的全部内容（包括 `index.html`、`cn.html`、`assets/`）作为部署包。

### 步骤 2：Vercel 控制台操作
1. 登录 [Vercel](https://vercel.com/dashboard)
2. **Add New → Project → Upload**（拖拽整个文件夹）
   - 或连接 Git 仓库（推荐，支持后续 push 自动部署）
3. 项目设置：
   - **Framework Preset**：Other / Static Site
   - **Build Command**：留空（纯静态站点，无需构建）
   - **Output Directory**：`.`（根目录）
   - **Install Command**：留空
4. 点击 **Deploy**

### 步骤 3：绑定域名 `seedwool.com`
1. 项目设置 → **Domains** → 添加 `seedwool.com` 和 `www.seedwool.com`
2. 配置 DNS：
   - A 记录 `@` → Vercel 提供的 IP
   - CNAME `www` → Vercel 分配的域名
3. Vercel 自动颁发 SSL 证书（HTTPS）

### 步骤 4：中文站点访问
中文页访问路径：`https://seedwool.com/cn.html`

## 上传后验收清单

- [ ] `index.html` HTTP 状态码 200（英文首页）
- [ ] `cn.html` HTTP 状态码 200（中文首页）
- [ ] 英文 Hero 主图（水稻.jpg）正常显示
- [ ] 4 款产品卡片全部渲染（育苗块 / 种植垫 / 水稻育秧体系 / 多孔纤维棉）
- [ ] 阿里国际站 iframe 正常嵌入（`hbshengding.en.alibaba.com`）
- [ ] 3 张证书图片正常（营业执照 / 省级科技成果证书 / 国家级科技成果登记证书）
- [ ] 4 个数据看板图表正常显示
- [ ] 4 个合作伙伴 Logo 位置正常（未下载则显示“Logo 待补充”）
- [ ] 批次验真弹窗可正常打开和验证
- [ ] 符合性判定演示可正常输入并判定 A/B/C
- [ ] 页脚显示 `SeedWool™`（无 `®`）
- [ ] 无价格、毛利、ROI 数值出现在公开页
- [ ] 2 张新阿里商品图片本地显示（非热链 alicdn）

---

**打包位置**：`D:\Desktop\岩棉\SeedWool_网站上传包\`  
**生成时间**：2026-11-12 19:30 CST  
**基于**：Hermes 智能体战略规划 v2.8/v3.1、网站设计预览 v2、网站落地工程 v0.4、原始站点预览首页