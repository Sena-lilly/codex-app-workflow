# X Post Draft

公開後に `<GitHub repository URL>` を実際のURLへ差し替えてください。

## Single Post

Codexでアプリ開発を進めるためのOSSテンプレート `codex-app-workflow` を作りました。

実装、バグ調査、スレッド分割、TestFlight/App Store準備、handoff、安全確認のプロンプトとチェックリストをまとめています。

GitHub: `<GitHub repository URL>`

## Thread Draft

### Post 1

Codexでアプリ開発を進めるためのOSSテンプレート `codex-app-workflow` を作りました。

実装だけでなく、調査、レビュー、リリース準備、長いセッションのhandoffまで扱うワークフローキットです。

GitHub: `<GitHub repository URL>`

### Post 2

作った理由:

Codexは便利ですが、長い開発では文脈が混ざったり、リリース判断や外部送信のような副作用操作が曖昧になりがちです。

そこで、作業開始時に貼れるプロンプトと、確認ルールをテンプレート化しました。

### Post 3

対象:

- iOS個人開発者
- SwiftUI開発者
- Backend付きアプリ開発者
- TestFlight/App Store review前の確認を型にしたい人
- Codexの長い作業セッションを安全に管理したい人

### Post 4

入っているもの:

- Core Codex templates
- Agent role prompts
- Thread templates
- App Store / TestFlight / Privacy / IAP checklists
- Safety standards
- 実例つきExamples

### Post 5

Examplesでは、iOS feature、Backend bug investigation、App Store release readiness、session handoffの流れを入れています。

「何を貼るか」「Codexに何を調査させるか」「どう出力させるか」まで見えるようにしました。

### Post 6

Safety standardsでは、GitHub push、release作成、外部API送信、本番DB書き込み、App Store/TestFlight操作などを高リスク操作として扱います。

必要な場合は、target / payload / impact scope / rollback plan を先に出すルールです。

### Post 7

Known limitations:

これは実行可能なフレームワークではなく、ドキュメントとテンプレート集です。

法務・Privacy・App Store・IAPまわりはチェックリストであり、法的助言ではありません。

まだ初期版なので、使いながら改善していきます。

### Post 8

まずは `README.md` の Start Here と `docs/quickstart-paths.md` から見るのがおすすめです。

GitHub: `<GitHub repository URL>`

## Short Variants

### Variant A

Codexでアプリ開発を進めるためのテンプレート集を作りました。

実装、バグ調査、release準備、thread分割、human confirmation、handoffを扱います。

GitHub: `<GitHub repository URL>`

### Variant B

Codexにアプリ開発を手伝ってもらうとき、毎回プロンプトや安全確認をゼロから考えないための土台を作りました。

`codex-app-workflow`

GitHub: `<GitHub repository URL>`

### Variant C

Codex向けのApp Store/TestFlight準備テンプレート、thread管理、agent role、safety checklist、examplesをまとめたOSSです。

まずは `initial-audit.md` から使えます。

GitHub: `<GitHub repository URL>`

