---
description: Akamai ホスティングを使用する場合は、コンソールから未発行のルールをテストします。
keywords: Dynamic Tag Management, ルール, switcher プラグイン, akamai, akamai のテスト, 未発行のルール, 未発行のルールのテスト, ルールのデバッグ
seo-description: Akamai ホスティングを使用する場合は、コンソールから未発行のルールをテストします。
seo-title: Akamai ホスティング用の未発行のルールのテスト
solution: Experience Cloud, Analytics, Target, Dynamic Tag Management
title: Akamai ホスティング用の未発行のルールのテスト
uuid: 979e3d74-8d96-47d0-b581-cf5371248434
translation-type: ht
source-git-commit: e060fb745d611f37f28708b3fe103c1191aa483b

---


# Akamai ホスティング用の未発行のルールのテスト

Akamai ホスティングを使用する場合は、コンソールから未発行のルールをテストします。

多くの場合、Switcher プラグインを使用すると最も簡単にテストを実施できます。詳しくは、Dynamic Tag Management 製品ドキュメントの「[Search Discovery プラグイン](https://marketing.adobe.com/resources/help/ja_JP/dtm/search_discovery_plugins.html)」を参照してください。

Switcher プラグインを使用せずにテストする方法を次に示します。

1. サイトの Web コンソールにアクセスして、「`localStorage.setItem('sdsat_stagingLibrary', true)`」と入力します。
1. **[!UICONTROL Enter]** を押します。
1. 「`_satellite.setDebug(true)`」と入力してから、**[!UICONTROL Enter]** キーを押します。
1. ページを更新します。

   このアクションにより、ステージング用ライブラリが読み込まれ、デバッガーが設定されるので、ページで実行される使用可能なすべての（発行された／未発行の）ルールの詳細が確認できます。
1. 終了したら、`localStorage.setItem('sdsat_stagingLibrary', false)` を実行し、**[!UICONTROL Enter]** キーを押します。

   手順の結果