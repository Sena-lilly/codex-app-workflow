# Zenn Article Draft

公開後に `<GitHub repository URL>` を実際のURLへ差し替えてください。

## タイトル案

Codexでアプリ開発を進めるためのワークフローキットを作った

## 本文

`codex-app-workflow` というOSSテンプレートを作りました。

GitHub: `<GitHub repository URL>`

これは、Codexを使ってアプリ開発を進めるときのためのプロンプト、ロール定義、スレッド分割ルール、リリース前チェックリスト、実例をまとめたワークフローキットです。

大きな目的は、Codexに作業を任せる範囲を広げながらも、文脈管理・安全確認・リリース判断を曖昧にしないことです。

## なぜ作ったか

Codexは、リポジトリを読んだり、ローカルコマンドを実行したり、ファイルを編集したりできます。

一方で、アプリ開発では次のような判断が何度も出てきます。

- まず何を調査させるべきか
- どのファイルを触ってよいか
- どの作業は別スレッドに分けるべきか
- どの時点で人間確認が必要か
- TestFlightやApp Store提出前に何を見るべきか
- 長い作業セッションをどう引き継ぐか

毎回その場で考えると抜け漏れが出やすいので、よく使う流れをテンプレート化しました。

## 誰向けか

主な対象は次のような開発者です。

- iOS個人開発者
- SwiftUI開発者
- FastAPIなどのBackend付きアプリを作っている開発者
- Codexを使って実装、調査、レビュー、リリース準備まで進めたい人
- TestFlightやApp Store review前の確認を少し体系化したい人

## 何が入っているか

大きく分けると、次のものが入っています。

- Codexへそのまま貼るためのCore templates
- CEO / PM / Engineer / QA / Release Manager / Legal ReviewのAgent templates
- iOS / Backend / Release / Bugfix向けのThread templates
- App Store / TestFlight / Privacy / IAP / SafetyのChecklists
- 実際の流れを示すExamples
- human confirmation / rollback / sensitive information audit のSafety standards

## 最初に見る場所

初見の場合は、まず `README.md` の `Start Here` を見てください。

迷ったら最初にコピーするテンプレートはこれです。

- `templates/codex/initial-audit.md`

目的がはっきりしている場合は、`docs/quickstart-paths.md` から自分の状況に近いルートを選べます。

用意しているルートは次の通りです。

- 既存アプリを監査したい
- 新機能を実装したい
- バグを調査したい
- TestFlight準備をしたい
- App Store review準備をしたい
- 長いCodexセッションを安全に管理したい

## Examples

Examplesでは、単なる説明ではなく次の流れを入れています。

1. Scenario
2. Goal
3. Starting prompt
4. Recommended template
5. Expected workflow
6. Expected output
7. Handoff example
8. Common mistakes
9. Done criteria

現在の例は次の4つです。

- iOS feature workflow
- Backend bug investigation
- App Store release readiness
- Release session handoff

## Safety standards

このリポジトリでは、副作用のある操作を高リスクとして扱います。

たとえば次のような操作です。

- GitHub push
- release作成
- 外部API送信
- 本番DB書き込み
- App Store提出
- TestFlight操作
- 課金・価格変更

これらが必要な場合、Codexには実行前に次を提示させる設計にしています。

- target
- payload or operation details
- impact scope
- rollback plan

Codexに作業してもらうほど、このあたりの確認を雑にしないことが大事だと思っています。

## Known limitations

現時点では、これは実行可能なフレームワークではなくドキュメントとテンプレート集です。

また、App Store、プライバシー、法務、IAPまわりの内容は運用チェックリストであり、法的助言ではありません。

テンプレートは汎用的に作っているため、実際のプロジェクトではコードベースやチームの運用に合わせて調整してください。

まだv0.1.0相当なので、実プロジェクトで使いながら改善していく前提です。

## まとめ

Codexを使ったアプリ開発では、実装力だけでなく、文脈管理・確認ルール・リリース前の慎重さも必要になります。

`codex-app-workflow` は、そのあたりを毎回ゼロから考えないための土台として作りました。

GitHub: `<GitHub repository URL>`

