# Brawl Stars Hub

繁體中文荒野亂鬥資訊整理網站，使用 GitHub Pages + Supabase。

## 功能

- 公開瀏覽官方消息、活動消息、維護資訊與社群整理
- 版本更新紀錄
- 角色圖鑑
- 管理員登入後台（僅允許列入 Supabase `admin_users` 的帳號寫入）
- 手機優先的響應式版面

## 技術

- 單頁前端：HTML / CSS / JavaScript
- 資料庫與驗證：Supabase
- 部署：GitHub Pages

## 安全

- 前端只使用 Supabase publishable key。
- 不將 Supabase secret / service_role key 放進瀏覽器或 GitHub。
- 所有公開資料表均啟用 RLS。
- 訪客只能讀取已發布內容；只有 `admin_users` 中的使用者可新增、修改或刪除內容。
- 一般訪客不需要登入。

## Supabase 資料表

- `news_posts`
- `game_updates`
- `brawlers`
- `admin_users`

## 管理員設定

先在 Supabase Auth 建立管理員帳號，再將該帳號的 Auth user UUID 加入 `public.admin_users(user_id)`。網站管理入口只提供登入，不提供公開註冊。

## 注意

本網站為非官方粉絲資訊整理網站，與 Supercell 無隸屬或官方合作關係。遊戲名稱及相關素材權利歸其各自權利人所有。
