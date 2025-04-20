# VS Codeのエディタ活用ナレッジ

## 警告・エラーチェックの重要性
- 新しいコードを書いたり、既存のコードを修正したりする前に、**VSCodeのエディタ内の警告・エラー表示を必ずチェックする**
- VSCodeは非常に優れた静的解析機能を持っており、多くの問題を事前に検出してくれる
- 特に以下のような問題を早期発見できる：
  - 非推奨になったAPIや設定（例: terminal.integrated.enableBellの代わりにterminal.integrated.enableVisualBellを使うなど）
  - シンタックスエラーやタイプミス
  - 未使用の変数や関数
  - インポートの問題
  - TypeScript/JavaScript固有のエラー

## ターミナル設定のベストプラクティス
- 新しいターミナルがどんどん作られるのを防ぐための設定:
  ```json
  "terminal.integrated.enablePersistentSessions": true,
  "terminal.integrated.persistentSessionReviveProcess": "never",
  "terminal.integrated.splitCwd": "inherited",
  "terminal.integrated.defaultLocation": "editor"
  ```

- 非推奨になった設定は速やかに新しい推奨設定に置き換える:
  ```json
  // 非推奨: "terminal.integrated.enableBell": false
  // 推奨:
  "terminal.integrated.enableVisualBell": false,
  "accessibility.signals.terminalBell": false
  ```

## その他のVS Code設定のベストプラクティス
- プロジェクト固有の設定は `.vscode/settings.json` に置く
- 全プロジェクト共通の設定はユーザー設定に置く
- 設定の変更は即時適用されるが、一部の設定はVS Codeの再起動が必要