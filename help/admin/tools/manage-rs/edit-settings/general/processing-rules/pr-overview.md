---
description: 処理ルールはデータ収集をシンプル化し、レポーティングに送信されるコンテンツを管理します。
subtopic: Processing rules
title: 処理ルールの概要
feature: Processing Rules
role: Admin
exl-id: 0244aba2-4345-463a-8528-d4dcd2f872ff
TQID: https://experienceleague.adobe.com/fiWUPrFezgDFX-mx-ogHH1wXYgtUF9vAgLjay9z6vsU
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: b4dd41a7-ccf8-4e9d-918e-acaab534a307id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: d3cdead0-685a-4489-9250-4bb709942f66id: eddd9b14-83bd-4ff4-9072-54a4a484abb7
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 661
ht-degree: 3%

---

# 処理ルールの概要

処理ルールを使用すると、データがレポートスイートに書き込まれる前に、データの収集方法を変更できます。

**[!UICONTROL 管理者]** > **[!UICONTROL レポートスイート]** > レポートスイートを選択> **[!UICONTROL 設定を編集]** > **[!UICONTROL 一般]** > **[!UICONTROL 処理ルール]**

>[!WARNING]
>
>処理ルールはデータ収集に直接影響し、誤って使用されるとデータ損失が発生する可能性があります。 実稼動レポートスイートで処理ルールを有効にする前に、常に開発レポートスイートの処理ルールをテストして、データ品質の問題を軽減します。

処理ルールの主な使用例は、次のふたつです。

* **コンテキストデータ変数実装ワークフローを使用**：実装で変数を直接設定する代わりに、[ コンテキストデータ変数](/help/implement/vars/page-vars/contextdata.md)を使用してキーと値のペアを設定できます。 例えば、次のように設定する代わりに、

  ```js
  s.eVar1 = "Robert Munch";
  s.eVar2 = "Books";
  s.eVar3 = "Youth";
  ```

  代わりに、次を設定できます。

  ```js
  s.contextData['author'] = "Robert Munch";
  s.contextData['section'] = "Books";
  s.contextData['genre'] = "Youth";
  ```

  次に、Analytics UIでコンテキストデータ変数を目的のディメンションと指標にマッピングできます。

  組織内の開発者と通信してプロパティにAnalyticsを実装する場合、コンテキストデータ変数を使用すると、通信プロセスが簡素化されます。 開発者は、各キーと値のペアを1回実装するだけで、Analytics管理者は、データが正しい実装変数に到達することを確認できます。

* **収集されたデータを変更する**：このユースケースには、データ品質の一時的な修正や、実装のギャップを埋めるための支援など、幅広いアプリケーションがあります。 詳細と具体的な例については、[処理ルールのユースケース ](pr-use-cases.md)を参照してください。

## 権限

製品管理者は、デフォルトで処理ルールにアクセスできます。 **[!UICONTROL 処理ルール]**&#x200B;の権限項目を含む製品プロファイルに処理ルールを含めることで、管理者以外のユーザーに処理ルールへのアクセス権を付与できます。 詳しくは、「[ レポートスイートツールの製品プロファイル権限](/help/admin/admin-console/permissions/report-suite-tools.md)」を参照してください。

## 処理ルールの作成または編集時の考慮事項

処理ルールを作成または編集する際には、次の点を考慮してください。

* **空の値**：ルールを作成する場合、上書き値が空の場合を考慮してください。 例えば、eVar2でeVar1を上書きし、eVar2が空の場合、両方の変数は空白になります。 Adobeでは、変数値を使用して別の値を上書きする前に、変数値をチェックする条件を追加することをお勧めします。
* **保存時にすぐに適用**：処理ルールは、収集したデータを保存した瞬間に適用されます。 既に収集されたデータにさかのぼって適用されることはありません。
* **ルール内の処理順序**：複数の処理ルールがある場合、それらのルールを実行する順序は重要です。 特定の変数を複数のルールで使用する場合は、それらの変数が正しい順序で実行されていることを確認してください。 ルール 1でeVar3を上書きすると、その元のeVar3値は後続のルールでは使用できません。
* **データ収集パイプライン内の処理順序**: Adobe Analyticsでのデータの処理順序[を参照して、データ収集パイプライン全体の処理ルールが適用される場所を把握してください。](/help/technotes/processing-order.md)
* **エンコーディング**：ほぼすべての場合でUTF-8 エンコーディングに従います。
* **大文字と小文字の区別**：処理ルールの文字列比較では、大文字と小文字が区別されません。 値を上書きするために使用する文字列値は、変数に直接入力するのと同じルールを使用します。
* **単一のレポートスイート**：処理ルールを編集する場合、1つのレポートスイートにのみ適用されます。 レポートスイートマネージャーで複数のレポートスイートを選択すると、1つのレポートスイートを選択する必要があります。 目的の処理ルールを作成または編集したら、それらのルールを[他のレポートスイートにコピーできます](pr-copy.md)。
* **データ除外なし**: データの除外は、処理ルールの意図された機能ではありません。 データ収集レベルで[`abort`](/help/implement/vars/config-vars/abort.md)を使用するか、データ収集後に[VISTA ルール ](/help/technotes/vista.md)を使用することを検討してください。
* **使用可能な変数**：すべてのディメンションと指標が処理ルールで使用できるわけではありません。 サポートされている機能の完全なリストについては、[処理ルール ](pr-variables.md)で使用できるディメンションと指標を参照してください。
* **許可されるルールの数**：各レポートスイートには最大150個のルールを含めることができます。 各ルールには最大30個の条件を含めることができます。

>[!MORELIKETHIS]
>
>![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [処理ルールを使用して、コンテキスト データ変数をpropとeVarにマッピング ](https://experienceleague.adobe.com/en/docs/analytics-learn/tutorials/implementation/implementation-basics/map-contextdata-variables-into-props-and-evars-with-processing-rules){target="_blank"}
