# プロジェクト用語集 (Glossary)

## 概要
Next.js / Supabase スタックにおけるプロジェクト用語を定義します。

## ドメイン用語

### AI 判断 (Gemini Judgment)
最新の株価指標に基づき Gemini が生成する売買推奨。

### 仮想資産 (Virtual Assets)
ユーザーの profiles テーブルで管理される擬似的な資金。

## 技術用語 (Stack)

### Server Actions
Next.js 14+ の機能。ブラウザからサーバー上の非同期関数を直接呼び出す仕組み。Gemini API 呼び出し等に使用。

### RLS (Row Level Security)
Supabase (PostgreSQL) の機能。ユーザー ID に基づき、データの読み書き権限を制御する。

### shadcn/ui
Radix UI と Tailwind CSS をベースにした、コピー＆ペースト可能なコンポーネントライブラリ。

## ステータス

### 取引状態 (Trade Status)
- **Pending**: Gemini 判断待ち。
- **Completed**: 取引完了、DB 記録済み。
- **Failed**: API エラー等による失敗。
