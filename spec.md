# Resume Portfolio Website Spec

## 目標
建立一個單頁履歷型 portfolio 網站，採用 Apple Liquid Glass 風格，適用 GitHub Pages 部署。網站必須符合 104 / 1111 人力銀行 2025-2026 對履歷視覺建議，並支援手機與桌機閱讀。

## 技術限制
- 單一 `index.html` 檔案
- CSS 內嵌在 `<style>` 中
- 不使用 React / Vue / 任何打包工具
- 使用純 HTML/CSS/少量原生 JavaScript（若需要 TOC 平滑捲動）

## 內容區塊與順序
1. Hero（頭像 + 名字 + 一句話定位 + 求職方向 pills）
2. About 關於我（2-3 段自介 + 求職方向 / 所在地 / 語言）
3. Skills 核心技能（分類成多組，每組 tag 雲）
4. Education 學歷（timeline 樣式）
5. Experience 經歷（timeline 樣式，含數字化成果）
6. Awards 競賽獎項（卡片 grid，含獎項 emoji badge）
7. Projects 作品集（卡片 grid）
8. Contact 聯絡（4 顆按鈕：Email / GitHub / LinkedIn / IG）

## 全站設計風格
- Apple Liquid Glass 風格
  - 玻璃材質感背景
  - 柔和漸層、淡雅霧面、光澤高亮
  - 乾淨留白與層次分隔
  - 現代極簡字型與柔圓按鈕
- 版面必須對手機與桌機都好看
  - 桌機採雙欄或卡片排版
  - 手機採單欄收縮、段落留白良好
- 浮動 TOC 導覽列固定於畫面頂端或側邊
  - 支援快速跳到各區塊
  - 在手機上可收合或顯示簡潔標籤

## 區塊內容細節
### 1. Hero
- 左側/上方放頭像圓形
- 右側/下方放姓名、職稱定位、一句話
- 求職方向 pills：AI 工程師、FinTech、顧問業、科技業

### 2. About
- 2-3 段自我介紹，涵蓋個人特色、求職目標、學校背景與職能
- 快速資訊欄：求職方向、所在地、語言

### 3. Skills
- 分成多組技能群組，例如：Programming、AI / ML、Data、Tools、Soft Skills
- 每組以 tag 雲呈現，tag 有玻璃卡片或微浮動效果

### 4. Education
- Timeline 樣式呈現學歷與時間
- 節點設計要有年份、學校、科系、重點描述

### 5. Experience
- Timeline 樣式呈現實習 / 專案經歷
- 包含數字化成果，例如：提升 XX%、處理 XX 筆資料、專案成效

### 6. Awards
- 卡片 grid 呈現
- 每張卡片包含獎項名稱、年份、簡短說明
- 使用 emoji badge 增加視覺趣味

### 7. Projects
- 卡片 grid 呈現作品
- 每張卡片含作品標題、類別、描述、技術重點
- 若有，可模擬作品連結按鈕（GitHub / Demo）

### 8. Contact
- 4 個按鈕：Email、GitHub、LinkedIn、Instagram
- 按鈕樣式統一，含 icon / 文字

## 可達成的互動
- 浮動 TOC 能快速導覽
- Section 標題可對應 anchor id
- 可加入簡單滑動動態（CSS 過渡、卡片 hover）

## Apple Liquid Glass 設計規格（CSS Only 升級）

### 核心視覺要素

#### 1. **背景漸層（Background Motion）**
- 基礎背景色：深藍 `#0c1120`
- 兩層 radial-gradient 漸層光暈：
  - 第一層：深藍 `rgba(120, 202, 255, 0.18)` 左上漸出
  - 第二層：紫粉 `rgba(135, 95, 255, 0.2)` 右下漸出
- 頂層 linear-gradient：深藍漸層 `#09101f` → `#0b121f`
- 動畫效果（可選）：使用 `@keyframes` 讓漸層光暈緩慢飄動（3-5s 循環）

#### 2. **玻璃卡片（Glass Panel）**
- 背景：半透明白底 `rgba(255, 255, 255, 0.08)` ～ `rgba(255, 255, 255, 0.12)`
- 邊框：1px 半透明白邊 `rgba(255, 255, 255, 0.12)` ～ `rgba(255, 255, 255, 0.14)`
- 模糊效果：`backdrop-filter: blur(24px)` （macOS Big Sur 標準值）
- 圓角：`border-radius: 28px` ～ `32px`
- 陰影：柔和多層 `box-shadow: 0 30px 80px rgba(0, 0, 0, 0.25)` + inset 亮邊效果（可選）

#### 3. **Hover 卡片浮起效果（Soft Glow Float）**
- 基礎：向上平移 `transform: translateY(-4px)` ～ `translateY(-6px)`
- 邊框發光：`border-color` 升高透明度至 `rgba(149, 214, 255, 0.28)` ～ `rgba(149, 214, 255, 0.32)`
- 陰影增強：添加外部 glow `box-shadow: 0 0 24px rgba(120, 210, 255, 0.15)`（可疊加）
- 過渡動畫：`transition: transform 0.25s ease, border-color 0.25s ease, box-shadow 0.25s ease`

#### 4. **Timeline 樣式**
- **垂直軸**：左側 `border-left: 2px solid rgba(120, 210, 255, 0.2)` + **glow 效果** `box-shadow: inset 0 0 16px rgba(120, 210, 255, 0.1)`
- **圓點節點**：
  - 寬高：`12px × 12px`
  - 背景：漸層 `linear-gradient(180deg, #7fd9ff, #5ab5ff)`
  - 發光環：`box-shadow: 0 0 0 6px rgba(120, 210, 255, 0.12), 0 0 16px rgba(120, 210, 255, 0.08)`
  - 位置：左側 18px 固定
- **時間文字**：`var(--accent)` 色，`0.92rem` 字級，`letter-spacing: 0.08em`

#### 5. **Tag 雲（Tag Cloud / Capsule）**
- **外觀**：膠囊狀 `border-radius: 999px`
- **背景**：半透明 `rgba(255, 255, 255, 0.08)` ～ `rgba(149, 214, 255, 0.12)`
- **邊框**：1px 清楚可讀 `rgba(255, 255, 255, 0.12)` ～ `rgba(255, 255, 255, 0.14)`（控制透明度保持可讀性）
- **Hover 效果**：輕微上升 `transform: translateY(-2px)` + 背景色提升
- **字級**：`0.92rem` ～ `0.95rem`，顏色 `#f2f7ff` ～ `#eaffff`
- **Gap**：`10px` flex 間距

#### 6. **文字對比度（Accessibility）**
- 主文字（h1, h2）：`#ffffff` 或 `var(--text)` `#f5f7fb`
- 副文字：`var(--muted)` `#d9e0ff`
- 標籤文字：`#eaf4ff` ～ `#eaffff`
- 最小 WCAG AA 對比度要求：4.5:1

### 色彩系統（色票）
```
--bg: #0c1120              // 深藍背景
--panel: rgba(255, 255, 255, 0.12)    // 卡片基礎
--panel-strong: rgba(255, 255, 255, 0.18)  // 卡片強調
--border: rgba(255, 255, 255, 0.14)   // 邊框標準
--text: #f5f7fb            // 主文字
--muted: #d9e0ff           // 副文字
--accent: #96d6ff          // 強調色（淡藍）
--accent-strong: #75c6ff   // 強調色深
--shadow: 0 30px 80px rgba(0, 0, 0, 0.25)  // 標準陰影
```

### 動畫規範
- 標準過渡時間：`0.25s ease`
- 背景動畫：✅ **不使用**（保持靜態漸層）
- Easing Function：主要用 `ease` / `ease-in-out`

### RWD 斷點
- 桌機：1180px max-width
- 平板：900px 下調整
- 手機：640px 單欄

---

## 待你確認項目
- ✅ 背景動畫：保持靜態漸層
- ✅ Timeline 左側軸線：邊框 + glow 雙效果
- ✅ Tag 雲邊框：清楚可讀（控制透明度）
- ✅ Contact 連結：dummy 文字（不填實際連結）
- ✅ Projects 卡片：不需要 GitHub/Demo 按鈕
- ✅ 是否同意使用「王小明 / 中原大學資管系」作為假資料範例？
- ✅ 玻璃卡片 hover 浮起效果需要「邊框+發光+陰影 glow」三重效果

## 交付內容
- `index.html`（只修改 `<style>` 區塊，嚴格遵守 CSS-Only 升級）
- `spec.md`（此版本）

---

**下一步**：請確認以上 Apple Liquid Glass 設計規格已符合您的要求。確認後我會 **僅修改 `<style>` 區塊**，實現：
1. 玻璃卡片 hover 浮起 + 邊框發光 + 陰影 glow（三重效果）
2. Timeline 左側垂直軸線 + glow 內發光
3. 標籤膠囊清楚可讀（控制透明度）
4. 所有視覺細節符合 macOS Big Sur / iOS Control Center 質感