---
title: Try JJazzLab with the latest translation files
date: '2018-07-07T09:53:27.000Z'
draft: false
---

# テスト中の翻訳

次のJJazzLab公式リリースまで待ちきれないという方は、どのような見ばえかを確かめるために最新翻訳ファイルでJJazzLabを試してみたくなるかもしれませんね。

まず、[以下の手順](https://jjazzlab.gitbook.io/developer-guide/build-from-source-code)に従ってソースコードからJJazzLab-Xをビルドします。ただし、以下に説明するように、マスターブランチの代わりに **l10n\_master**ブランチを使用してください。

### JJazzLab-XコードのソースプロジェクトをGitHubから取得する

1. メニューで**Team→Git→Clone**と進みます。
2. リポジトリアドレスを**https://github.com/jjazzboss/JJazzLab-X.git**と入力します。 ****
3. ユーザーとパスワードは空白のままにしておいてください。
4. **Next**を押して**l10n\_master** \(l10n とは "localization"の意味\)ブランチ「だけ」を選択してください。
5. Netbeans が**JJazzLab-X**プロジェクトをクローンファイルから開きます。

{% hint style="info" %}
The **l10n\_master** branch is a localization branch where Crowdin automatically pushes new translation files. Note that this synchronization is done **every hour**, so you may not see the latest changes. Also, if there are several translation candidates for one source phrase, **only the validated one is pushed**. If no translation is validated yet, Crowdin uses the first candidate.
{% endhint %}



