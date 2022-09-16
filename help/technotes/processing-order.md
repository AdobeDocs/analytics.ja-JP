---
title: Adobe Analyticsでのデータの処理順序
description: Adobe Analyticsでデータを処理するコンポーネントやサービスの順序について説明します。
source-git-commit: 65ee7ae6d838f34149eb60547d976856e4da3b17
workflow-type: tm+mt
source-wordcount: '584'
ht-degree: 0%

---

# Adobe Analyticsでのデータの処理順序

Adobeは、レポートに表示される前にデータを変更または操作する多くの方法を提供します。 このページでは、様々なAdobe Analytics機能がデータを処理する順序を示します。 このリストを使用して、データの不整合をトラブルシューティングしたり、データの調整が必要な場合に使用する最適な機能を決定したりできます。

## Adobeに送信する前のデータ

データがAdobeに送信される前に、通常、次のいずれかの方法を使用してクライアント側でコンパイルされます。

* **AppMeasurement**:サイトでホストされ、各ページで参照される JavaScript ファイル。 データはAdobe Analyticsに直接送信されます。
* **Adobe Experience Platform Web SDK**:サイトでホストされ、各ページで参照される JavaScript ファイル。 データが Adobe Experience Edge に送信されます。
* **Adobe Experience Cloud Data Collection のタグ**:各ページの JavaScript 参照。データ収集 UI 内で作成されたルールが含まれます。 Adobe Analytics拡張機能を使用すると、AppMeasurement を簡単に実装できます。 Web SDK 拡張機能を使用すると、Web SDK をより簡単に実装できます。

Adobe Experience Edge にデータを送信する場合、Adobe Analytics( および他の多くのAdobe Experience Cloudソリューション ) にデータを転送するように設定できます。 実装方法に関係なく、最終的には、目的の変数を持つイメージリクエストがAdobeデータ収集サーバーに送信されます。

## Adobe Analyticsデータ収集サーバーに送信されるデータ

データがAdobe Analyticsに届くと、次の機能によって必要に応じてデータが調整されます。

1. **参照テーブル**:Adobe内部ルックアップテーブルに依存するDimension( 例： [ブラウザー](/help/components/dimensions/browser.md) ディメンション ) は、対応する値に一致します。
2. [**動的変数**](/help/implement/vars/page-vars/dynamic-variables.md):動的変数がイメージリクエストの任意の部分で表示される場合、その値はコピーされ、独立した値として扱われます。
3. [**ボットルール**](/help/admin/admin/bot-removal/bot-rules.md):標準またはカスタムのボットフィルタリングを適用して、そのデータをレポートから除外します。
4. [**処理ルール**](/help/admin/admin/c-processing-rules/processing-rules.md):組織でデータに適用されるカスタムルール。 次のマッピングを含む： [コンテキストデータ変数](/help/implement/vars/page-vars/contextdata.md) をそれぞれの変数に追加します。
5. **VISTA ルール**:Adobeコンサルタントによってデータに適用される柔軟なカスタムルール。 VISTA ルールは、組織のニーズに応じて、処理ルールの前後に実行される可能性があります。 ほとんどの VISTA ルールは、通常、処理ルールの後に実行されますが、各組織の設定は異なります。 既存の VISTA ルールの詳細については、Adobeのアカウントマネージャーにお問い合わせください。
6. [**マーケティングチャネルの処理ルール**](/help/components/c-marketing-channels/c-rules.md):以下を使用できます。 [処理ルール](/help/admin/admin/c-processing-rules/processing-rules.md) を使用して、マーケティングチャネルの処理ルールで使用するデータを準備します。
7. **位置情報データ**:IP アドレス参照に依存するDimension( 例： [国](/help/components/dimensions/countries.md) ディメンション ) が入力されます。
8. [**IP Obfuscation（IP の不明化）**](/help/admin/admin/general-acct-settings-admin.md):生データの IP アドレスを難読化することを選択した場合は、他のすべての処理機能が完了した後におこなわれます。

この時点で、個々のヒットがレポートスイートのデータテーブルに記録されます。 標準の [待ち時間](latency.md) 間隔の場合は、レポートで使用できます。

## 処理後のデータの変更

Adobe Analyticsのデータは、ほとんど永続的です。ただし、一部の機能では、選択的なデータの調整や削除が可能です。

* [**データ修復 API**](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/data-repair/):特定の列を編集するか、目的のデータ行を削除します。
* [**データガバナンス**](/help/admin/c-data-governance/an-gdpr-workflow.md):データを恒久的に削除するプライバシーリクエストに対応します。
* [**分類**](/help/components/classifications/c-classifications.md):ルールまたはアップロードされたデータに基づいてディメンションを作成し、異なる方法でデータを整理できるようにします。 基になるレポートスイートのデータは変更されないので、自由に分類データを編集または上書きできます。
* [**仮想レポートスイート**](/help/components/vrs/vrs-about.md):訪問のタイムアウトを変更または [クロスデバイス分析](/help/components/cda/overview.md).
