---
title: タグの Analytics プロパティの作成
description: タグを使用してスペースを作成し、データの収集方法をカスタマイズします。
feature: Tags
exl-id: ffcd8e97-4d29-489e-bc2b-88805400dad5
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '500'
ht-degree: 97%

---

# Adobe Analytics タグプロパティの作成

Adobe Experience Platform のタグを使用すると、web サイト上で Experience Cloud ソリューションを統合できます（Analytics を含む）。このページでは、タグ管理者が Adobe Analytics の基本的な実装を正しく設定する方法について詳しく説明します。

## 前提条件

[レポートスイートの作成](/help/admin/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md)：収集する Analytics データ用のサイロを作成します。

## タグプロパティを作成し、重要な拡張機能をインストール

プロパティは、タグの管理に使用する包括的なコンテナです。拡張機能を使用すれば、製品固有のタグをインストールして設定できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 「**[!UICONTROL 新規プロパティ]**」をクリックします。
1. プロパティに Web サイトのタイトルなどの名前を付け、Analytics を実装するドメインを入力します。「**[!UICONTROL 保存]**」をクリックします。
1. 新しく作成したタグプロパティをクリックして、設定を入力します。
1. 「**[!UICONTROL 拡張機能]**」タブをクリックし、「**[!UICONTROL カタログ]**」をクリックします。
1. 「Experience Cloud ID サービス」を見つけ、「**[!UICONTROL インストール]**」をクリックします。
1. Experience Cloud 組織 ID を含むすべての設定は、既に入力されているはずです。「**[!UICONTROL 保存]**」をクリックします。
1. 拡張機能カタログに戻り、Adobe Analytics を探して「**[!UICONTROL インストール]**」をクリックします。

詳しくは、[Adobe Analytics 拡張機能](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/analytics/overview.html?lang=ja)の完全なドキュメントを参照してください。

## Adobe Analytics 用のデータ要素の作成

データ要素は、変数値を収集するための、サイトの特定の部分に対する参照です。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. サイトに実装するタグプロパティをクリックします。
1. 「**[!UICONTROL データ要素]**」タブをクリックしてから、「**[!UICONTROL データ要素の追加]**」をクリックします。
1. データ要素に次の設定を指定します。

   * 名前：ページ名
   * 拡張機能：Core
   * データ要素の種類：JavaScript 変数
   * JavaScript 変数名：`window.document.title`

     >[!NOTE]
     >
     >この値は、開始を支援するための例として提供されます。データレイヤーの値など、ページ名に適した値を組織が定義する場合は、ここに入力できます。
   * クリーンテキストの確認
   * 保存期間：なし
1. 「**[!UICONTROL 保存]**」をクリックします。

## Adobe Analytics のルールの作成

ルールは、データ要素を Analytics 変数値にマッピングし、それらの値がアドビのサーバーに送信されるタイミングを決定します。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. サイトに実装するタグプロパティをクリックします。
1. 「**[!UICONTROL ルール]**」タブをクリックしてから、**[!UICONTROL ルールを追加]**&#x200B;をクリックします。`Global Rule` という名前を付けます。
1. イベントの横にある「**[!UICONTROL 追加]**」をクリックし、次の設定を入力します。
   * 拡張機能：Core
   * イベントタイプ：読み込まれたライブラリ（ページ上部）
   * 名前：Core - 読み込まれたライブラリ（ページ上部）
1. 「**[!UICONTROL 変更を保存]**」をクリックします。
1. 「**[!UICONTROL アクション]**」で、「**[!UICONTROL 追加]**」をクリックし、次の設定を入力します。
   * 拡張機能：Adobe Analytics
   * アクションタイプ：変数を設定
   * ページ名：コンテナアイコンをクリックし、`Page Name`データ要素を選択します
   * キャンペーン：値が `cid` のクエリパラメーター
1. 「**[!UICONTROL 変更を保存]**」をクリックします。
1. アクションの横のプラス記号をクリックして別のアクションを追加し、次の設定を入力します。
   * 拡張機能：Adobe Analytics
   * アクションタイプ：ビーコンを送信
   * 名前：Adobe Analytics - ビーコンを送信
   * トラッキング：s.t()
1. 「**[!UICONTROL 変更を保存]**」をクリックします。
1. イベントと 2 つのアクションが設定されていることを確認し、「**[!UICONTROL 保存]**」をクリックします。

## 次の手順

[Analytics 実装を開発環境にデプロイする](deploy-dev.md)：テスト環境で Analytics コードを使用します。
