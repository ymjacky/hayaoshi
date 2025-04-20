# タスク001 - index.htmlにQRコード表示機能を追加する

## 背景
現在、index.htmlはシンプルな表示だけで、管理画面に遷移するための機能がない。

## 目的
QRコードを使って別ページ(manager.html)に遷移できるようにし、システム操作の幅を広げる。UUIDをパラメータに含めることで、セッション管理やデータ連携を可能にする。

## 作業内容
1. server.tsにUUID生成機能を追加する
   - `@std/uuid`を使ってUUIDを生成するメソッドを作成
   - `/api/uuid`エンドポイントを追加してUUIDを提供する

2. index.htmlにQRコード表示機能を追加する
   - CDN経由でqrcode-generatorライブラリを導入
   - QRコード表示用のHTML要素を追加
   - クライアントサイドのJavaScriptでQRコードを生成・表示

## 受け入れ条件
- server.tsでUUIDが正しく生成され、APIから取得できること
- index.htmlにQRコードが表示されること
- QRコードをスキャンするとmanager.html?uuid=XXXXにアクセスできること

## 注意事項
- manager.htmlは別タスクで作成するため、現時点では存在しなくてもOK
- QRコード生成はクライアントサイドで行い、サーバー負荷を減らす
- UUIDは十分なランダム性を持つv4を使用