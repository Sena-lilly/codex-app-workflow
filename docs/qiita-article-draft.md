# Qiita Article Draft

公開後に `<GitHub repository URL>` を実際のURLへ差し替えてください。

## タイトル案

Codexでアプリ開発するときの「人間確認」と「安全な作業分割」をテンプレート化した

## はじめに

Codexを使ってアプリ開発を進めるためのテンプレート集 `codex-app-workflow` を作りました。

GitHub: `<GitHub repository URL>`

この記事では、リポジトリ全体の紹介に加えて、特に次の2点を中心に書きます。

- Codexの作業をどう分割するか
- 副作用のある操作をどう人間確認に戻すか

## 背景

Codexにアプリ開発を手伝ってもらうと、調査、実装、テスト、レビュー、リリース準備まで見通しよく進めやすくなります。

ただし、便利さと同時に次のようなリスクもあります。

- 長いスレッドで文脈が混ざる
- 実装、調査、リリース判断が同じ会話に入りすぎる
- DB書き込みや外部送信のような副作用操作が曖昧になる
- App Store / TestFlight / GitHub releaseまわりの作業を勢いで進めそうになる
- 途中で何を決めたか分からなくなる

そこで、Codex向けのプロンプトとチェックリストをワークフローとして整理しました。

## 誰向けか

このリポジトリは、次のような人向けです。

- iOS個人開発者
- SwiftUI開発者
- Backend付きアプリを開発している人
- FastAPIなどのAPIサーバーも含めてCodexに見てもらいたい人
- TestFlightやApp Store review前の確認を型にしたい人

## 入っているもの

主な構成は次の通りです。

- `templates/codex/`: Codexへ貼る作業別プロンプト
- `templates/agents/`: CEO / PM / Engineer / QA / Release Manager / Legal Reviewのロールプロンプト
- `templates/threads/`: iOS / Backend / Release / Bugfixなどのスレッド開始テンプレート
- `templates/checklists/`: App Store、TestFlight、Privacy、IAP、Safetyなどのチェックリスト
- `examples/`: 実際の流れを示すサンプル
- `docs/`: philosophy、thread management、release management、safety standardsなど

## Examples

Examplesには次のような流れを入れています。

- iOS feature workflow
- Backend bug investigation
- App Store release readiness
- Release session handoff

それぞれ、開始プロンプト、期待される調査、期待される出力、handoff例まで含めています。

単なる読み物ではなく、Codexに貼って使うイメージを持てるようにしています。

## Safety standards

特に重視しているのは、人間確認ルールです。

次のような操作は、Codexが勝手に実行しない前提にしています。

- create
- update
- delete
- approve
- reject
- send
- publish
- release
- deploy
- production database writes
- external API sends
- GitHub push
- App Store / TestFlight operations

これらの操作が必要な場合は、実行前に次を提示するルールにしています。

- target
- payload or operation details
- impact scope
- rollback plan

たとえば「TestFlightへアップロードして」ではなく、Codexにはまず「どの画面で、何を、どの範囲に影響させ、どう戻すか」を説明させる、という考え方です。

## 使い始め方

初めて使う場合は、次の順番がおすすめです。

1. `README.md`
2. `docs/quickstart-paths.md`
3. `templates/codex/initial-audit.md`
4. 自分の作業に近い `examples/`

既存アプリを見てもらうなら、まず `initial-audit.md` をCodexに貼るのが一番分かりやすいです。

## Known limitations

このリポジトリは、アプリのコード生成フレームワークではありません。

また、法務・プライバシー・App Store審査・IAPまわりの記述はチェックリストであり、法的助言ではありません。

テンプレートは汎用的なので、実際にはプロジェクトの構成、チームルール、リリースフローに合わせた調整が必要です。

まだ初期版なので、実運用で使いながら改善していく前提です。

## まとめ

Codexを使うと、アプリ開発の調査や実装を進めやすくなる場面があります。

ただ、そのぶん「どこまで任せるか」「どこで人間が確認するか」「どう安全に引き継ぐか」を明文化しておく価値も増えると感じています。

`codex-app-workflow` は、そのための小さな土台です。

GitHub: `<GitHub repository URL>`
