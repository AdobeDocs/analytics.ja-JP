---
title: Web SDK JavaScript ライブラリを使用したAdobe Analyticsへのデータの送信
description: まず、JavaScript ライブラリを使用してAdobe Analyticsにデータを送信する、クリーンな Web SDK の実装から始めます。
hide: true
hidefromtoc: true
source-git-commit: d4c9bddf18311e13d025ed9d62c0636a33eb7b85
workflow-type: tm+mt
source-wordcount: '602'
ht-degree: 0%

---

# Web SDK JavaScript ライブラリを使用したAdobe Analyticsへのデータの送信

この実装パスには、Web SDK JavaScript ライブラリを使用した新規 Web SDK インストールが含まれます。 その他の実装パスについては、次の別のページで説明しています。

* [Web SDK タグ拡張機能](web-sdk-tag-extension.md):Web SDK タグ拡張機能を使用した新規 Web SDK インストール。 Web SDK JavaScript ライブラリのアプローチ（このページ）と同様に、Adobe Experience Platform Data Collection のタグを使用して実装を管理する点が異なります。 これには、XDM スキーマに含める一般的な Analytics 変数を含むAdobe Analytics ExperienceEvent フィールドグループが必要です。
* [Analytics 拡張機能から Web SDK 拡張機能へ](analytics-extension-to-web-sdk.md):Adobe Analytics タグ拡張機能から Web SDK タグ拡張機能に移行するためのスムーズで系統的なアプローチを採用します。 このアプローチにより、Customer Journey AnalyticsなどのAdobe Experience Platform サービスを使用する準備が整うまで XDM を使用する必要がなくなります。 の使用 `data` の代わりにのオブジェクト `xdm` Adobeにデータを送信するオブジェクト。
* [Web SDK JavaScript ライブラリのAppMeasurement](appmeasurement-to-web-sdk.md)：タグを使用しない点を除き、Web SDK に移行するためのスムーズで系統立ったアプローチ。 代わりに、Adobe Analytics データ収集ライブラリ（`AppMeasurement.js`）を選択し、Web SDK JavaScript ライブラリ（`alloy.js`）に設定します。

## この実装パスのメリットとデメリット

Web SDK JavaScript ライブラリを使用してAdobe Analyticsにデータを送信する場合、メリットとデメリットの両方があります。 各オプションを慎重に検討し、組織に最適なアプローチを決定します。

| メリット | デメリット |
| --- | --- |
| <ul><li>**直接アプローチ**：この実装パスは、既存のAdobe Analytics実装を移行するアプローチよりも簡単です。 現在Adobe Analyticsの実装を心配する必要がない場合は、該当する Web SDK XDM フィールドに値を入力します。</li><li>**定義済みスキーマ**：組織で独自のスキーマが必要ない場合は、Adobe Analytics向けのスキーマを使用するだけです。 この概念は、Customer Journey Analyticsに向かう途中でも当てはまります。prop と eVar の概念はCustomer Journey Analyticsには当てはまりませんが、prop と eVar を単純なカスタムディメンションとして引き続き使用できます。</li></ul> | <ul><li>**実装を変更するには、開発者の介入が必要です**:Web SDK 実装を変更する場合は、開発チームと協力してサイトのコードを編集する必要があります。 を使用するアプローチ [Web SDK タグ拡張機能](web-sdk-tag-extension.md) この欠点を回避します。</li><li>**特定のスキーマを使用してにロック**：組織がCustomer Journey Analyticsに移行する場合、Adobe Analytics スキーマを引き続き使用するか、独自の組織のスキーマ（個別のデータセット）に移行するかを選択する必要があります。 Customer Journey Analyticsへの移行時にAdobe Analytics スキーマと個別のデータセットへの移行の両方を避けたい場合、Adobeでは次の 2 つの方法のいずれかを推奨します。</li><ul><li>の使用 `data` オブジェクト：です `data` オブジェクトを使用すると、XDM スキーマに準拠せずにAdobe Analyticsにデータを送信できます。 組織のスキーマが作成されたら、データストリームマッピングを使用してマッピングできます `data` オブジェクトフィールドを XDM に変換します。 両方 [Analytics 拡張機能から Web SDK 拡張機能へ](analytics-extension-to-web-sdk.md) および [Web SDK JavaScript ライブラリのAppMeasurement](appmeasurement-to-web-sdk.md) これを使用 `data` オブジェクト。</li><li>Adobe Analyticsを完全にスキップする：Web SDK を実装している場合は、そのデータをAdobe Experience Platformのデータセットに送信して、Customer Journey Analyticsで使用できます。 任意のスキーマを使用できます。Adobe Analyticsは、このワークフローにはまったく関与しないので、Adobe Analytics ExperienceEvent フィールドグループは必要ありません。 この方法では、最低限の技術的負債しか発生しませんが、Adobe Analyticsは完全に全体像から外れています。</li></ul></ul> |
