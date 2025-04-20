# Denoプロジェクトの知見

## APIドキュメントの調べ方
- `deno doc [モジュールURL]` コマンドでAPIの使い方を調べられる
- 例: `deno doc https://deno.land/std/uuid/mod.ts` でUUIDモジュールの使い方が確認できる
- 標準ライブラリのAPIは `deno doc --builtin` で一覧表示できる

## 依存関係の管理
- deno.jsoncファイルで依存関係を管理する
- importマップを使って、URLをエイリアスにマッピングできる
- 不要な依存関係はパフォーマンスのために削除すべき（例: crypto.randomUUID()を使うようになったら@std/uuidは不要）

## Tailwind CSS関連
- Tailwind CSSの変更を反映するには `deno task dev:all` を使う
- このコマンドはサーバー起動とCSS監視の両方を行う
- CSSの変更は自動的に反映される

## その他のTips
- サーバーのポートがすでに使用中のエラー「Address already in use (os error 48)」が出た場合は、`pkill -f "deno run"` で既存のプロセスを終了させる
- deno.jsonc内のタスク定義を活用すると作業が捗る