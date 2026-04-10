# 開発ガイドライン (Development Guidelines)

## コーディング規約

### 言語・フレームワーク
- **TypeScript**: `strict: true` を前提とし、型安全性を最大限に活用。
- **React**: Functional Components + Hooks。

### 命名規則
- **Variable/Function**: `camelCase`
- **Component**: `PascalCase`
- **Constant**: `UPPER_SNAKE_CASE`

### Server Actions
- 非同期処理および副作用（DB更新、API呼び出し）は Server Actions 内で行う。
- エラー内容は UI 側でハンドリングできるよう、適切な戻り値（またはシリアライズ可能なエラーオブジェクト）を返す。

## スタイリング・UI
- **Tailwind CSS**: ユーティリティクラスを活用。
- **shadcn/ui**: コンポーネントが必要になったら `npx shadcn-ui@latest add [component]` で追加する。

## データベース (Supabase)
- **Migrations**: スキーマ変更は `supabase db remote commit` またはローカルでの migration ファイル作成で行う。
- **Types**: `supabase gen types` を活用し、DB スキーマと TypeScript 型を同期させる。

## テスト
- **Vitest**: ロジック、ユーティリティのユニットテスト。
- **Playwright**: 主要なユーザーストーリーの E2E テスト。

## 開発プロセス
1. **GitHub ブランチ**: `main` から機能ごとに `feature/` ブランチを作成。
2. **PR レビュー**: 変更内容とテスト結果を明記。
3. **自動デプロイ**: `main` へのマージで Vercel へ自動反映。
