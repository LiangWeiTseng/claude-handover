# claude-session-skills

Claude Code 的 session 管理 slash commands，幫助你在切換任務或結束工作前，快速整理交班摘要、清理 context 雜訊。

## 包含的 Skills

| 指令 | 說明 | 何時用 |
|------|------|--------|
| `/save` | Context 健康檢查 + 交班單 + 問你要不要 /clear | 切換任務前、session 結束前 |
| `/wrap` | 同 `/save`（別名） | 同上 |
| `/handover` | 只產生交班單 + 更新 WORKLOG | 想單獨交班，不做 context 分析 |
| `/context-check` | 掃記憶檔、找雜訊、出精簡報告 | 每 3-4 session 做一次維護 |

## 安裝方式

### 個人使用（user-level）

```bash
# Clone 這個 repo
git clone https://github.com/YOUR_USERNAME/claude-session-skills.git

# 複製 commands 到你的 Claude Code 全域設定
cp -r claude-session-skills/.claude/commands/* ~/.claude/commands/
```

Windows 使用者：

```powershell
Copy-Item -Recurse "claude-session-skills\.claude\commands\*" "$env:USERPROFILE\.claude\commands\"
```

### 團隊共用（project-level）

把 `.claude/commands/` 資料夾直接放進你的專案 repo 並 commit，所有人 clone 後就能使用。

## 推薦工作流程

```
開始 session
  → 做任務

要切換主題 or 快結束
  → /save   ← 一個指令搞定收尾
  → /clear  ← 清 context（/save 會提醒你）

每 3-4 session
  → /context-check  ← 單獨做記憶維護
```

## License

MIT
