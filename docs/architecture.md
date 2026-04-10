# 技術仕様書 (Architecture Design Document)

## テクノロジースタック

### 開発基盤

| 技術 | 用途 | 選定理由 |
|------|------|----------|
| Next.js (App Router) | Web フレームワーク | 高速なレンダリングと Server Actions によるシンプルなバックエンド連携。 |
| TypeScript | 言語 | 型安全性の確保。 |
| Supabase | BaaS (DB/Auth) | PostgreSQL の利用と、認証/DB構築の迅速化。 |
| Vercel | デプロイメント | Next.js との親和性が最も高く、CI/CD が容易。 |

### ライブラリ

| 技術 | 用途 |
|------|------|
| shadcn/ui | UI コンポーネント |
| Tailwind CSS | スタイリング |
| Lucide React | アイコン |
| Zod | バリデーション |
| Recharts | データ可視化 |

## アーキテクチャパターン

### Next.js App Router アーキテクチャ

```text
┌──────────────────────────────┐
│       Next.js App Layer      │
│ ┌────────┐    ┌────────────┐ │
│ │ Client │    │ Server     │ │
│ │ Compts │←──→│ Actions    │ │
│ └────────┘    └─────┬──────┘ │
└─────────────────────┼────────┘
                      ▼
            ┌──────────────────┐
            │  External Cloud  │
            │ ┌──────┐ ┌──────┐│
            │ │Gemini│ │S'base││
            │ └──────┘ └──────┘│
            └──────────────────┘
```

#### Client Components
- UI の対話性とステート管理。
- データの表示とフォーム入力。

#### Server Actions
- ビジネスロジックの実行（Gemini 呼び出し、DB更新）。
- 秘密情報（APIキー）の安全な取り扱い。
- データの再検証（Revalidation）。

## データ永続化戦略

### ストレージ方式
- **PostgreSQL (Supabase)**: 取引履歴、ユーザープロフィール。
- **Cookies/Session**: 認証トークン管理。

## セキュリティ
- **環境変数**: `GOOGLE_API_KEY`, `SUPABASE_SERVICE_ROLE_KEY` 等は Vercel の Environment Variables で管理。
- **RLS (Row Level Security)**: Supabase のポリシーを使用し、自分のデータのみアクセス可能にする。

## デプロイ・運用
- **CI/CD**: GitHub Actions または Vercel GitHub Integration。
- **Monitoring**: Vercel Analytics / Speed Insights。

## 開発ガイドライン (基本方針)
- コンポーネントの責務を明確に分ける。
- 型定義を徹底し、 `any` の使用を避ける。
- Server Actions 内でエラーハンドリングを行い、UI に適切なフィードバックを返す。
