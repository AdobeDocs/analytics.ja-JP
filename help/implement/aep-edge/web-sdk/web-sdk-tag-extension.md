---
title: Web SDK タグ拡張機能を使用したAdobe Analyticsへのデータの送信
description: まず、XDM とAdobe Analytics ExperienceEvent フィールドグループを使用してAdobe Experience Platform データ収集からAdobe Analyticsにデータを送信する、クリーンなデータ収集の実装から始めます。
hide: true
hidefromtoc: true
source-git-commit: d4c9bddf18311e13d025ed9d62c0636a33eb7b85
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 0%

---

# Web SDK タグ拡張機能を使用したAdobe Analyticsへのデータの送信

この実装パスには、Adobe Experience Platform Data Collection のタグを使用した新規の Web SDK インストールが含まれます。 その他の実装パスについては、次の別のページで説明しています。

* [Web SDK JavaScript ライブラリ](web-sdk-javascript-library.md):Web SDK JavaScript ライブラリを使用した新規 Web SDK インストール（`alloy.js`）に設定します。 Web SDK タグ拡張機能アプローチ（このページ）と同様に、タグ UI を使用する代わりに自分で実装を管理する点が異なります。 これには、XDM スキーマに含める一般的な Analytics 変数を含むAdobe Analytics ExperienceEvent フィールドグループが必要です。
* [Analytics 拡張機能から Web SDK 拡張機能へ](analytics-extension-to-web-sdk.md):Adobe Analytics タグ拡張機能から Web SDK タグ拡張機能に移行するためのスムーズで系統的なアプローチを採用します。 このアプローチにより、Customer Journey AnalyticsなどのAdobe Experience Platform サービスを使用する準備が整うまで XDM を使用する必要がなくなります。 の使用 `data` の代わりにのオブジェクト `xdm` Adobeにデータを送信するオブジェクト。
* [Web SDK JavaScript ライブラリのAppMeasurement](appmeasurement-to-web-sdk.md)：タグを使用しない点を除き、Web SDK に移行するためのスムーズで系統立ったアプローチ。 代わりに、手動でAdobe Analytics データ収集ライブラリ（`AppMeasurement.js`）を選択し、Web SDK JavaScript ライブラリ（`alloy.js`）に設定します。

## この実装パスのメリットとデメリット

Web SDK 拡張機能を使用してAdobe Analyticsにデータを送信する方法には、メリットとデメリットの両方があります。 各オプションを慎重に検討し、組織に最適なアプローチを決定します。

| メリット | デメリット |
| --- | --- |
| <ul><li>**最も直接的なアプローチ**：この実装パスは最もわかりやすいパスであり、通常は新しい Web SDK 実装の推奨パスになります。 現在Adobe Analyticsの実装を心配する必要がない場合は、該当する Web SDK XDM フィールドに値を入力します。</li><li>**定義済みスキーマ**：組織で独自のスキーマが必要ない場合は、Adobe Analytics向けのスキーマを使用するだけです。 この概念は、Customer Journey Analyticsに向かう途中でも当てはまります。prop と eVar の概念はCustomer Journey Analyticsには当てはまりませんが、prop と eVar を単純なカスタムディメンションとして引き続き使用できます。</li><li>**開発者の操作なしでタグを管理**：タグを使用すると、開発者に実装のコード変更を要求せずに実装を管理できます。 開発者がタグローダースクリプトをインストールすると、データの収集方法を完全に制御できます。</li></ul> | <ul><li>**特定のスキーマを使用してにロック**：組織がCustomer Journey Analyticsに移行する場合、Adobe Analytics スキーマを引き続き使用するか、独自の組織のスキーマ（個別のデータセット）に移行するかを選択する必要があります。 Customer Journey Analyticsへの移行時にAdobe Analytics スキーマと個別のデータセットへの移行の両方を避けたい場合、Adobeでは次の 2 つの方法のいずれかを推奨します。<ul><li>の使用 `data` オブジェクト：です `data` オブジェクトを使用すると、XDM スキーマに準拠せずにAdobe Analyticsにデータを送信できます。 組織のスキーマが作成されたら、データストリームマッピングを使用してマッピングできます `data` オブジェクトフィールドを XDM に変換します。 両方 [Analytics 拡張機能から Web SDK 拡張機能へ](analytics-extension-to-web-sdk.md) および [Web SDK JavaScript ライブラリのAppMeasurement](appmeasurement-to-web-sdk.md) これを使用 `data` オブジェクト。</li><li>Adobe Analyticsを完全にスキップする：Web SDK を実装している場合は、そのデータをAdobe Experience Platformのデータセットに送信して、Customer Journey Analyticsで使用できます。 任意のスキーマを使用できます。Adobe Analyticsは、このワークフローにはまったく関与しないので、Adobe Analytics ExperienceEvent フィールドグループは必要ありません。 この方法では、最低限の技術的負債しか発生しませんが、Adobe Analyticsは完全に全体像から外れています。</li></ul></ul> |


