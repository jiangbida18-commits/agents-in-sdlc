---
title: "レッスン 12 - GitHub Pages でサイトをデプロイする"
description: "GitHub Copilot アプリを使って Pages ワークフローを設定し、プルリクエストを確認して、公開された Space Quiz を検証します。"
authors:
  - jamesmontemagno
lastUpdated: 2026-10-12
---

GitHub Pages で Space Quiz をデプロイして、誰でもアクセスできるようにします。Copilot はワークフローを準備し、デプロイを案内できますが、変更を確認し、サイトが公開されたことを確認するのはユーザーの役割です。

このレッスンでは、次の操作を行います。

- Copilot に GitHub Pages のデプロイを設定するよう依頼します。
- ワークフローとプルリクエストをマージ前に確認します。
- デプロイの進行を追跡し、公開されたサイトを検証します。

## シナリオ

Space Quiz はすでに GitHub リポジトリにありますが、手軽に試せる方法が必要です。単一ファイルのサイトを GitHub Pages で公開すれば、サーバーやランタイム依存関係を追加せずに、公開された Uniform Resource Locator（URL）からアクセスできるようになります。

## Copilot にサイトのデプロイを依頼する

`space-quiz` の Copilot アプリのセッションで、次のプロンプトを送信します。

```plaintext
Enable GitHub Pages for this repository. Create a GitHub Actions workflow that builds the website if needed and deploys it to GitHub Pages. Add a README describing the app and how to run it locally if one does not already exist. Create a pull request with these changes and merge it after required checks pass. Monitor the deployment until it succeeds, then report the final URL of the live website. If you lack permission to enable Pages or merge, tell me exactly what I need to approve or do; do not report success until the site is live.
```

![3 段階の図: マージ済みの space-quiz プルリクエスト、Build website、Upload artifact、Deploy to Pages の各ステップを含む GitHub Actions の Deploy website 実行成功、yourname.github.io/space-quiz/ で公開された Space Quiz。](../../../_images/first-steps-app-pages-deploy.svg)

> [!WARNING]
> このプロンプトは、エージェントにプルリクエストの作成とマージ、およびリポジトリの Pages 設定変更を依頼します。続行する前に、差分、デプロイ権限、GitHub による承認要求を確認してください。

## ワークフローを確認してデプロイを検証する

マージする前に、ワークフローが意図したとおりに動作し、デプロイが正常に完了することを確認します。

1. リポジトリに `README` がまだない場合に限り、`README` が追加されていることを確認します。
2. ワークフローのビルド手順とデプロイ手順を含め、プルリクエストの変更を確認します。
3. 必須のプルリクエストチェックがすべて成功してからマージします。
4. GitHub Actions のデプロイ実行が成功するまで進行状況を確認します。
5. 報告された URL を開き、Space Quiz が表示されることを確認します。

エージェントが Pages の有効化やプルリクエストのマージを実行できない場合は、提示された具体的な手順に従います。デプロイが成功し、公開サイトが読み込まれるまで、タスクを完了扱いにしないでください。

## まとめと次のステップ

次の作業を完了しました。

- Copilot に GitHub Pages のデプロイを設定するよう依頼しました。
- マージ前にワークフローとプルリクエストを確認しました。
- デプロイを追跡し、公開されたサイトを検証しました。

続けて[レッスン 13: まとめと次のステップ][next-lesson]に進みます。

[next-lesson]: ../13-review/
