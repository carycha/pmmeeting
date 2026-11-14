# PMMeeting

> 把 **OpenSpec**（spec-driven development）與 **Superpowers**（TDD / 軟體工程紀律）深度整合進 **Pi Coding Agent** 的單一 package：`/pmmeeting` 一條命令，走完 explore → design → propose → plan → build(TDD) → verify → archive 的全流程。

**狀態：設計完成，待確認後進入實作。**

## 設計文件（確認後才動工）

| 文件 | 內容 |
|---|---|
| [docs/01-上游研究報告.md](docs/01-上游研究報告.md) | Pi v1.5.2 / Superpowers v7.0.2 / OpenSpec 2.0.0 機制查核 + 社群 prior art |
| [docs/02-整合對照表.md](docs/02-整合對照表.md) | Phase ↔ 雙上游對照、重複工件消解裁定、CLI 調用表 |
| [docs/03-workflow設計.md](docs/03-workflow設計.md) | 狀態機、gate 定義（G1-G6）、完整 workflow 圖 |
| [docs/04-核心架構設計.md](docs/04-核心架構設計.md) | 目錄結構、extension 設計、7 個關鍵決策（各附替代方案） |
| [docs/05-實作計畫.md](docs/05-實作計畫.md) | Phase 0-6 任務分解 + 驗收標準 |
| [docs/06-風險評估.md](docs/06-風險評估.md) | 風險清單（等級/依據/緩解/殘餘）+ 待拍板項 |

## 核心設計一句話

- **OpenSpec 擁有文件**（`openspec/` 樹是唯一真相來源）；**Superpowers 提供紀律**（15 個 skills vendored、byte-identical、pin v7.0.2）；**PMMeeting 負責編排**（extension = 狀態機 + gate 機制，orchestrator skill = phase 判斷與工件重導向契約）。
- **免預裝**：OpenSpec CLI 以 npm dependency pin 進套件（Pi 安裝時自動裝）；Superpowers skills vendored 進 repo（lockfile + checksum）。
- **不重複勞動**：brainstorming 的 design doc 直接寫成 OpenSpec 的 `design.md`，writing-plans 的 plan 直接寫成 `tasks.md` — 全流程只有一套文件。
