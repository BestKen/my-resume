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

## 待你確認項目
- 是否同意使用「王小明 / 中原大學資管系」作為假資料範例
- 是否要保持 `Email / GitHub / LinkedIn / IG` 連結 placeholder，或填入示範連結
- 是否希望作品集卡片含「GitHub / Demo」按鈕（可選）

## 交付內容
- `index.html`（含內嵌 CSS / JS）
- `spec.md`

---

請確認以上 spec，確認後我再開始建立 `index.html`。