# リポジトリ構造定義書 (Repository Structure Document)

## プロジェクト構造

```
/
├── src/
│   ├── app/                # App Router (Pages, Layouts, Actions)
│   ├── components/         # UI Components
│   │   ├── ui/             # shadcn/ui (自動生成)
│   │   └── dashboard/      # 機能別コンポーネント
│   ├── lib/                # ユーティリティ、共有ライブラリ (Supabase client等)
│   ├── hooks/              # カスタムフック
│   ├── types/              # TypeScript 型定義
│   └── services/           # 外部 API 連携 (Gemini, Finance)
├── supabase/               # Supabase 関連 (Migrations, Types)
├── public/                 # 静的資産
├── tests/                  # テストコード
├── .env.local              # ローカル環境変数 (Git除外)
├── package.json            # 依存関係
└── tailwind.config.ts      # Tailwind 設定
```

## ディレクトリ詳細

### src/app/
- `page.tsx`: ルートページ。
- `actions.ts`: サーバーアクション定義。
- `(auth)/`: 認証関連のルートグループ。

### src/components/
- `ui/`: `npx shadcn-ui@latest add` で追加された基本パーツ。
- その他、関心事ごとにディレクトリを分割する。

### src/lib/
- `supabase.ts`: Supabase クライアントの初期化。
- `utils.ts`: Tailwind Merge 等の共通関数。

### src/services/
- `gemini.ts`: Gemini モデルの初期化と推論ロジック。
- `finance.ts`: 株価データの取得ロジック。

## 命名規則
- **コンポーネント**: `PascalCase.tsx`
- **関数・ユーティリティ**: `camelCase.ts`
- **ディレクトリ**: `kebab-case`

## 依存関係
- **UI → Actions**: Server Actions を利用して副作用を実行。
- **Actions → Services/Lib**: DB 処理や AI 連携。
