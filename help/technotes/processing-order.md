---
title: Adobe Analytics でのデータの処理順序
description: Adobe Analytics でデータを処理するコンポーネントとサービスの順序について説明します。
exl-id: a8dc9c12-07d3-4dc8-b2df-136f7a7a1e77
source-git-commit: 35e7c8bccb8524fa5e87cae223f0854956c7528a
workflow-type: tm+mt
source-wordcount: '588'
ht-degree: 100%

---

# Adobe Analytics でのデータの処理順序

アドビでは、レポートに表示される前にデータを変更または操作する方法を多数提供しています。このページでは、様々な Adobe Analytics 機能によるデータの処理順序を示します。このリストを使用すると、データの不整合をトラブルシューティングしたり、データの調整が必要な場合に使用する最適な機能を決定したりできます。

![処理順序](assets/processing-order.png)

## アドビに送信する前のデータ

データをアドビに送信する前に、次のいずれかのメソッドを使用すると、通常はクライアント側でコンパイルされます。

* **AppMeasurement**：サイトでホストされ、各ページで参照される JavaScript ファイル。データは Adobe Analytics に直接送信されます。
* **Adobe Experience Platform Web SDK**：サイトでホストされ、各ページで参照される JavaScript ファイル。データは Adobe Experience Edge に送信されます。
* **Adobe Experience Cloud データ収集のタグ**：データ収集 UI 内で作成されたルールを含む、各ページで参照される JavaScript ファイル。Adobe Analytics 拡張機能を使用すると、AppMeasurement の実装が容易になります。Web SDK 拡張機能を使用すると、Web SDK をより簡単に実装できます。

Adobe Experience Edge にデータを送信する場合、Adobe Analytics（および他の多くの Adobe Experience Cloud ソリューション）にデータを転送するように設定できます。実装メソッドに関係なく、最終的には必要な変数を含むイメージリクエストが Adobe データ収集サーバーに送信されます。

## Adobe Analytics データ収集サーバーに送信されたデータ

Adobe Analytics にデータを送信すると、必要に応じて次の機能でデータが調整されます。

1. **ルックアップテーブル**：アドビ内部のルックアップテーブルに依存するディメンション（[ブラウザー](/help/components/dimensions/browser.md)ディメンションなど）は、対応する値に一致します。
2. [**動的変数**](/help/implement/vars/page-vars/dynamic-variables.md)：イメージリクエストのいずれかの部分に動的変数が検出された場合、その値はコピーされ、独立した値として処理されます。
3. [**ボットルール**](/help/admin/admin/bot-removal/bot-rules.md)：標準またはカスタムのボットフィルタリングを適用すると、そのデータをレポートから除外できます。
4. [**処理ルール**](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md)：組織がデータに適用したカスタムルール。[コンテキストデータ変数](/help/implement/vars/page-vars/contextdata.md)のそれぞれの変数へのマッピングが含まれます。
5. **VISTA ルール**：アドビのコンサルタントがお客様のデータに適用する柔軟なカスタムルール。VISTA ルールは、組織のニーズに応じて、処理ルールの前または後に実行できます。通常、ほとんどの VISTA ルールは処理ルールの後に実行されますが、設定は組織ごとに異なります。既存の VISTA ルールについて詳しくは、アドビ担当営業または販売店にお問い合わせください。
6. [**マーケティングチャネルの処理ルール**](/help/components/c-marketing-channels/c-rules.md)：[処理ルール](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/c-processing-rules/processing-rules.md)を使用すると、マーケティングチャネルの処理ルールで使用するデータを準備できます。
7. **ジオロケーションデータ**：IP アドレスのルックアップに依存するディメンション（[国](/help/components/dimensions/countries.md)ディメンションなど）が入力されます。
8. [**IP の不明化**](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/general-acct-settings-admin.md)：組織が生データの IP アドレスを不明化することを選択した場合、他のすべての処理機能が完了した後に行われます。

この時点で、個々のヒットがレポートスイートのデータテーブルに記録されます。標準の[待ち時間](latency.md)間隔の後、レポートで使用できます。

## 処理後のデータの変更

Adobe Analytics のデータは、ほとんどが永続的です。ただし、一部の機能では、選択的なデータの調整や削除が可能です。

* [**Data repair API**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/)：特定の列を編集するか、目的のデータ行を削除します。
* [**データガバナンス**](/help/admin/c-data-governance/an-gdpr-workflow.md)：データを永続的に削除するプライバシーリクエストに対応します。
* [**分類**](/help/components/classifications/c-classifications.md)：ルールまたはアップロードされたデータに基づいてディメンションを作成し、異なる方法でデータを整理できるようにします。基になるレポートスイートのデータは変更されないので、自由に分類データを編集または上書きできます。
* [**仮想レポートスイート**](/help/components/vrs/vrs-about.md)：訪問のタイムアウトを変更したり、[クロスデバイス分析](/help/components/cda/overview.md)を許可したりできる別のレポートスイートビューを作成します。
