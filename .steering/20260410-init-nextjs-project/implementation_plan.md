# 実装計画: Next.js プロジェクトの初期化

## 概要
グローバルルールに基づき、Next.js (App Router), TypeScript, Tailwind CSS を使用したプロジェクトの土台を構築します。

## 背景
当初の Python 構成から、開発効率とスケーラビリティ、およびグローバルルールへの準拠を目的として、Next.js / Supabase 構成へ移行するため。

## 実装対象の機能
1. **Next.js プロジェクト初期化**: `npm init` 相当のベース構築。
2. **UI フレームワーク導入**: shadcn/ui のセットアップ。
3. **Supabase 連携**: Supabase SDK のインストールとクライアント設定。
4. **ディレクトリ構造の整理**: `src/` 配下のフォルダ分け。

## アーキテクチャ概要
- Framework: Next.js 14+ (App Router)
- Styling: Tailwind CSS
- Components: shadcn/ui
- DB/Auth: Supabase

## 依存ライブラリ
```json
{
  "dependencies": {
    "@supabase/supabase-js": "latest",
    "@supabase/ssr": "latest",
    "lucide-react": "latest",
    "zod": "latest"
  }
}
```

## 実装の順序
1. `npx create-next-app@latest ./` の実行（非対話モード）。
2. `npx shadcn-ui@latest init` の実行。
3. 必要なライブラリのインストール。
4. Supabase クライアント初期化コードの作成。
5. ディレクトリ構造を `repository-structure.md` に合わせる。
