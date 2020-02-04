---
description: Akamai ホスティングを使用する場合は、コンソールから未発行のルールをテストします。
keywords: Dynamic Tag Management;rule;switcher plug-in;akamai;test akamai;unpublished rules;test unpublished rules;debug rule
solution: Experience Cloud,Analytics,Target,Dynamic Tag Management
title: Akamai ホスティング用の未発行のルールのテスト
uuid: 979e3d74-8d96-47d0-b581-cf5371248434
translation-type: tm+mt
source-git-commit: 2ffa989156dd9bc4f6ef9a216e8c06425cc39440

---


# Akamai ホスティング用の未発行のルールのテスト

Akamai ホスティングを使用する場合は、コンソールから未発行のルールをテストします。

多くの場合、Switcherプラグインは最も簡単なテスト方法です。 See [Search Discovery plug-ins](https://marketing.adobe.com/resources/help/en_US/dtm/search_discovery_plugins.html) in the Dynamic Tag Management Product Documentation for more information.

次の手順は、Switcherプラグインを使用せずにテストする方法を示しています。

1. サイトの Web コンソールにアクセスして、「`localStorage.setItem('sdsat_stagingLibrary', true)`」と入力します。
1. **[!UICONTROL Enter]**を押します。
1. 「`_satellite.setDebug(true)`」と入力してから、**[!UICONTROL Enter]**キーを押します。
1. ページを更新します。

   このアクションにより、ステージング用ライブラリが読み込まれ、デバッガーが設定されるので、ページで実行される使用可能なすべての（発行された／未発行の）ルールの詳細が確認できます。
1. 終了したら、`localStorage.setItem('sdsat_stagingLibrary', false)` を実行し、**[!UICONTROL Enter]**キーを押します。

   手順の結果
