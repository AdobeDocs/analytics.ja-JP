---
description: Mobile Services の処理ルールを Adobe Analytics に移行する方法を説明します
title: Mobile Services の処理ルールの Adobe Analytics への移行
exl-id: ea183c1a-a85e-4f4e-a7f6-f947b939e9d9
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '686'
ht-degree: 100%

---

# Mobile Services の処理ルールの Adobe Analytics への移行

このドキュメントでは、Mobile Services UI で作成した追加の処理ルール（ライフサイクル指標を除く）を Adobe Analytics に移行する方法について説明します。

処理ルールは、コンテキストデータ変数の値を prop および eVar に移動するために使用されます。例えば、「検索語」コンテキストデータ変数の値をコマース変数 eVar の値に配置し、ヒットするたびにその値を上書きすることができます。 処理ルールがないと、Analytics にレポートが出力されないため、コンテキストデータ変数は無意味となります。

このドキュメントでは、Analysis Workspace でのモバイル使用レポートの実行方法についても説明します。

## 処理ルールの移行

処理ルールや使用レポート機能などの補完的な機能に Mobile Services を利用している場合は、Analytics UI（処理ルール UI または Analysis Workspace）にシームレスに移動して、これらの機能を実行できます。 ライフサイクル指標、または AA 処理ルール UI で設定されたルールの場合、移行をおこなう必要はありません。 ライフサイクル指標は、モバイル SDK が最初にアプリに実装されたときに自動的に収集される、「あらかじめ用意された」指標です。

ただし、Mobile Services UI（ライフサイクル指標を除く）で追加の処理ルールを設定した場合は、Mobile Services へのアクセス権を失った後に Analytics でその処理ルールを編集または削除できるように、それらの処理ルールを移行する必要があります。

1. `experience.adobe.com` にログインし、Mobile Services に移動します。
1. コンテキスト変数のマッピングを Adobe Analytics に移行するモバイルアプリの歯車アイコンをクリックします。
1. 「**[!UICONTROL 変数と指標を管理]**」メニュー項目をクリックし、「**[!UICONTROL カスタム変数]**」タブをクリックします。 ここでは、設定に追加されたコンテキスト変数マッピング（コンテキストデータ）を確認できます。 これらの設定をメモします（またはスクリーンショットを撮ります）。 例：

   ![コンテキスト変数](assets/context-var.png)

1. Experience Cloud で、Adobe Analytics に切り替え、Mobile Services で閲覧していたのと同じモバイルレポートスイートにいることを確認します。
1. **[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**／**[!UICONTROL 設定を編集]**／**[!UICONTROL 一般]**／**[!UICONTROL 処理ルール]**&#x200B;に移動します。
1. 「**[!UICONTROL Add Rule]**」をクリックします。
1. 条件を無視して、Mobile Services に存在するのと同じコンテキスト変数の追加に進みます。

   ![処理ルール](assets/proc-rule.png)

1. 「**[!UICONTROL 保存]**」をクリックします。

## Analysis Workspace でのモバイル使用レポート

Analysis Workspace には、モバイル指標とディメンション（レポートスイートが Mobile Services に対して有効になっている場合）に加えて、分析を促進するモバイルプロジェクトテンプレートがいくつか用意されています。

* **[!UICONTROL メッセージング]**：アプリ内およびプッシュメッセージングのパフォーマンスに焦点を当てています。
* **[!UICONTROL ロケーション]**： ロケーションデータを表示するマップを含みます。
* **[!UICONTROL 主要指標]**：アプリの主要指標の状況を把握します。
* **[!UICONTROL アプリ使用状況]**：アプリのアプリユーザー数、起動数、初回起動数、および平均セッション時間を示します。
* **[!UICONTROL 獲得]**：モバイル獲得リンクのパフォーマンスを示します。
* **[!UICONTROL パフォーマンス]**：アプリはどのように実行され、どこでユーザーにとって問題であったかを示します。
* **[!UICONTROL リテンション]**：常連ユーザーは誰で、これらのユーザーが何をしたかを示します。
* **[!UICONTROL ジャーニー]**：アプリでの主要な使用パターンを示します。

以下に、モバイルアプリの使用テンプレートの抜粋を示します。

![モバイルアプリの使用状況](assets/mobile-app-usage.png)

テンプレートにアクセスするには：

1. `experience.adobe.com` にログインし、「Analytics」を選択します。
1. Mobile Services が有効になっているレポートスイートを開いていることを確認します。
1. 「**[!UICONTROL Workspace]**」タブをクリックします。
1. 「**[!UICONTROL 新規プロジェクトを作成]**」をクリックします。
1. 任意のモバイルテンプレートを選択し、「**[!UICONTROL 作成]**」をクリックします。

## 他の Mobile Services 機能の移行

以下の Mobile Services 機能も Adobe Analytics と結び付けられていますが、購入済みのAdobe Analytics SKU が必要です。

* 「ダウンロード計測用リンク」
* プッシュメッセージ
* アプリ内メッセージ
* 目標地点管理

有料機能として Mobile Services を利用している場合、他の内部ツールおよび外部ツールへの実行可能な移行パスはありません。

* 獲得リンクについては、お客様のニーズを満たすためにアドビパートナーにご案内する場合があります。
* プッシュメッセージングおよびアプリ内メッセージングは、Adobe Campaign Standard と Adobe Campaign Classic で利用できます（プッシュのみ）。 ただし、ターゲティングに使用される基になるデータセットは異なります。 アドビアカウントチームと協力して、メッセージングデータの移行オプションを決定することをお勧めします。
* ロケーション機能については、すべての AEP のお客様に無料で提供される新しい [Adobe Experience Platform ロケーションサービス](https://www.adobe.com/jp/experience-platform/location-service.html)を採用することをお勧めします。
