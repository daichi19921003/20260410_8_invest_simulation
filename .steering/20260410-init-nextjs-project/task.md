# タスクリスト

## 🚨 タスク完全完了の原則
このファイルの全タスクが完了するまで作業を継続すること。

---

## フェーズ1: Next.js プロジェクト初期化
- [x] `npx create-next-app@latest` を実行
  - [x] TypeScript, ESLint, Tailwind CSS, App Router, src/ directory を有効化
- [x] 不要な初期ファイルの削除 (src/app/api/hello 等)

## フェーズ2: UI フレームワークセットアップ
- [x] `npx shadcn-ui@latest init` を実行
- [ ] 必要な基盤コンポーネントの追加 (button, card 等を想定)

## フェーズ3: バックエンド連携セットアップ
- [ ] Supabase 関連ライブラリをインストール
  - [ ] `@supabase/supabase-js`, `@supabase/ssr`
- [ ] `src/lib/supabase.ts` の作成（クライアント初期化）
- [ ] `.env.local` の設定確認

## フェーズ4: ディレクトリ構造の整理
- [ ] `src/services`, `src/types`, `src/hooks` ディレクトリの作成
- [ ] `repository-structure.md` に基づいた整合性確認

## フェーズ5: 品質チェックとデプロイ
- [ ] ビルドが成功することを確認 (`npm run build`)
- [ ] GitHub へのプッシュ
- [ ] Vercel デプロイ状況の確認

---

## 実装後の振り返り
### 実装完了日
2026-04-10

### 計画と実績の差分
(完了時に記載)

### 学んだこと
(完了時に記載)

### 次回への改善提案
(完了時に記載)
