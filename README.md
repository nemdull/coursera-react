# firstapp

プロジェクト概要
React アプリの雛形として Hello world 的な表示と Heading コンポーネントを用いた基本的な構造を示す。現状は最小構成で、今後の拡張ポイントを読み手に伝える設計思想を含む。

技術スタック
- 言語: JavaScript (ECMAScript 2021)
- フレームワーク/ライブラリ: React 18, React DOM, React Scripts (CRA 5.0.1)
- テスト: React Testing Library, Jest DOM, User Event
- ビルド/実行: Create React App（react-scripts）
- Lint/設定: ESLint 設定 (eslintConfig)
- 包含ファイル: package.json, package-lock.json, src/, public/
- CI/CD: 現状 CI 設定ファイルは本リポジトリには含まれていない想定（今後の追加を推奨）

主な機能一覧
- Hello world の見出しを表示する UI
- App.js は Heading コンポーネントをレンダリング
- Header と Heading の2つの小さなコンポーネント分割の設計
- App.test.js に React Testing Library を使ったテストの雛形が存在

設計・実装の工夫
- コンポーネント分割: Header, Heading の2つの小さなコンポーネントを用意
- テスト戦略の雛形: App.test.js はユニットテストの基本構造を示す
- 最小構成での SPA: ルート構成とコンポーネントの組み合わせによる単純な UI
- 設定の透明性: package.json の依存関係とスクリプトを明示

セットアップ & 動作確認方法
- ローカル環境
  - npm install
  - npm start で開発サーバ起動
  - npm test でテスト実行
- 動作確認の手順
  - ブラウザで http://localhost:3000 を開く
  - Heading がレンダリングされることを確認
- Docker 実行手順
  - Docker 化は現状想定外（別途検討推奨）
- 実行ログの確認
  - 変更や追加は、適切なコミットメッセージで追跡

改善ポイント / TODO（リポジトリから抽出し、カテゴリ分けして整理）
- テスト: App.test.js の期待文字列と表示内容の整合性を確認・修正
- 設計: Header コンポーネントの活用を拡張
- エラーハンドリング: ネットワークエラー等の取り扱いの追加検討
- CI/CD: lint/テストの自動実行を追加することを推奨
- ドキュメント: CONTRIBUTING や CODE_OF_CONDUCT の追加検討
- パフォーマンス/品質: テストカバレッジ拡張、静的解析・Lintルールの強化

強調したいポイント
- React 18 ベースの最小構成で、コンポーネント分割とテストの雛形を示している点
- 将来的な拡張性を意識した設計思想
