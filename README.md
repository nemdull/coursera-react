## FirstApp

数分で把握できる最小構成の React アプリ。Heading/ Header などの小さな関数コンポーネントと、CRA 標準のビルド・テスト体制を基盤に、学習・試作を素早く始められるように設計しています。

---

## 技術スタック

- 言語/ランタイム: JavaScript, Node.js
- ライブラリ: React 18 (`react`, `react-dom`)
- ビルド/開発: `react-scripts` 5 (Create React App)
- テスト: `@testing-library/react`, `@testing-library/jest-dom`, `@testing-library/user-event`
- パフォーマンス計測: `web-vitals`
- スタイル: `App.css`, `index.css`
- パッケージ管理: npm

根拠:
- 依存関係は `firstapp/package.json:1` に記載
- CRA 構成とスクリプトは `firstapp/package.json:12` の `scripts` を参照

---

## 主な機能

- Heading 表示: メイン画面に H1 見出しを表示（`firstapp/src/App.js:11`）
- StrictMode でのレンダリング: 予期せぬ副作用の検知（`firstapp/src/index.js:9`）
- Web Vitals 測定の導線: `reportWebVitals` を呼び出し（`firstapp/src/index.js:16`）
- PWA 関連メタデータ: `manifest.json` や各種アイコン（`firstapp/public/manifest.json:1`）

---

## 設計・実装の工夫

- 小さな関数コンポーネント: `Heading`/`Header` を関数として定義し、責務を限定（`firstapp/src/App.js:4`）
- 明確なエントリポイント: `App` が単一の UI を返し、拡張しやすい形に分離（`firstapp/src/App.js:11`）
- 標準的なテスト足場: `jest-dom` と Testing Library を導入済み（`firstapp/src/setupTests.js:1`）
- パフォーマンス測定の拡張性: Web Vitals を遅延 import で計測（`firstapp/src/reportWebVitals.js:1`）

ディレクトリのポイント:
- `src/` に UI/エントリ/テストを集約、`public/` に HTML/manifest/アイコンを配置（`firstapp/public/index.html:1`）

---

## セットアップ & 動作確認

前提: Node.js と npm をインストール済み。

- 依存関係インストール: `npm install`
- 開発サーバ起動: `npm start`（`http://localhost:3000`）
- 本番ビルド: `npm run build`
- テスト実行: `npm test`

メモ:
- パフォーマンス測定をログ出力する場合は、`firstapp/src/index.js:13` のコメントに従い `reportWebVitals(console.log)` を渡してください。

---

## 改善ポイント / TODO（事実に基づく）

- テスト: `App.test.js` は "learn react" に依存する初期テンプレートのまま（`firstapp/src/App.test.js:5`）。`Heading` の描画に合わせて期待値を更新し、`Header` も含めたユニットテストを追加。
- 設計: `Header` は未使用（`firstapp/src/App.js:14` のコメントアウト）。意図（将来利用/例示）を README に明文化、または UI に組み込むか削除を検討。
- アクセシビリティ: 見出し階層やランドマークの導入、`aria-*` の検討。
- CI/CD: GitHub Actions 等で `install -> lint -> test -> build` を自動化（本リポジトリにワークフローは未検出）。
- 品質: ESLint/Prettier のプロジェクトルールを明示化（必要に応じて設定ファイルを追加）。

---

## 強調したいポイント（スキル/工夫）

- テンプレート依存からの脱却と最小 UI 設計: 初期 CRA から不要要素をそぎ落とし、学習・検証に最適化。
- 拡張容易性: StrictMode・Testing Library・Web Vitals など将来の品質向上に繋がる足場を保持。
- 明示的な改善リスト: テスト/設計/CI の観点で次の一手を提示。

---

## 補足（ファイル参照）

- 依存関係とスクリプト: `firstapp/package.json:1`
- 入口 HTML: `firstapp/public/index.html:1`
- マニフェスト: `firstapp/public/manifest.json:1`
- ルート: `firstapp/src/index.js:1`
- アプリ本体: `firstapp/src/App.js:1`
- テスト: `firstapp/src/App.test.js:1`, `firstapp/src/setupTests.js:1`
- パフォーマンス: `firstapp/src/reportWebVitals.js:1`
