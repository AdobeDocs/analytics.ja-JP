---
description: Report Builder 5.2は、Adobe Analytics Unified Calculated Metricsをサポートしています。 これにより、すべての計算指標にグローバル ID が付けられ、複数のレポートスイートで使用することができるようになりました。
title: 計算指標
feature: Report Builder
role: User, Admin
exl-id: 462086eb-675f-443c-b3a6-b4fa390254da
TQID: https://experienceleague.adobe.com/Ae-k-aIMg3n3kXYWFngOzYihtlexLCoD5CmnEN3afhI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 396
ht-degree: 29%

---

# 計算指標

{{legacy-arb}}

Report Builder 5.2以降では、Adobe Analytics計算指標をサポートしています。 すべての計算指標にグローバル IDが追加されました。これらの指標は、1つのレポートスイートに制限されなくなりました。

>[!NOTE]
>
>既存のワークブックでは、従来の指標 ID の付いたリクエストを参照している場合があります。 Report Builder 5.2を使用すると、これらの従来の指標IDは新しいグローバル IDに変換されます。 Report Builder 5.1 を使用しているユーザーと共有した場合、計算指標は共有先で表示されません。

新しい計算指標ビルダーとマネージャーを使用して計算指標を作成および管理する方法について詳しくは、[計算指標](/help/components/calculated-metrics/cm-overview.md) ガイドを参照してください。

リクエストウィザードの手順2では、計算指標をフィルタリングして適用できます。

## 計算指標をフィルタリング {#section_376E986D3E684999A7CDB08E53854159}

**フィルター**&#x200B;は、フィルターアイコンをクリックして指標を計算しました：![&#x200B; アプリケーション、ユーザー、プロジェクトのフィールドを表示するフィルターオプションのスクリーンショット。](/help/admin/tools/assets/filter.png)

詳細フィルターダイアログには、標準の指標と計算された指標の両方が表示されます。

使用可能なフィルターは次のとおりです。

次の表に示す詳細フィルターのオプションを示す![&#x200B; スクリーンショット。](assets/advanced_filters.png)

| フィルター名 | 説明 |
|---|---|
| タグ | 特定のタグを持つ計算指標をフィルタリングできます。 タグフィルターでは、AND演算子が使用されます。 2つのタグをオンにすると、右側のペインに&#x200B;**両方**&#x200B;のタグが付けられた指標が表示されます。 |
| レポートスイート | 「*レポートスイート名*&#x200B;のみ」フィルターを [!DNL Adobe Analytics] の Calculated Metric Builder で適用し、[!DNL Report Builder] でアドバンスフィルターを表示すると、アドバンスフィルターでは、選択されたレポートスイートの計算指標のみが表示されます。 |
| 所有者 | 所有者ごとに指標をフィルタリングできます。 所有者フィルターはOR演算子を使用することに注意してください。 2人の所有者を確認すると、右側のペインに&#x200B;**いずれかの**&#x200B;所有者が所有する指標が表示されます。 |
| その他のフィルター／承認済み | すべての正式に承認された指標を表示します。 |
| その他のフィルター／お気に入り | お気に入りとしてマークしたすべての指標を表示します。 |
| その他のフィルター／自分が所有 | 所有するすべての指標を表示します。 |
| その他のフィルター／自分と共有 | 他のユーザーが共有したすべての指標が表示されます。 |

## 計算指標の適用 {#section_DF5CF349460A45FDA4B6E6BB8B52F18E}

フィルターを選択したら、**[!UICONTROL 適用]**&#x200B;をクリックしてリクエストに適用します。 選択した指標がレポートレイアウトに追加されました。

![&#x200B; リクエストウィザードの手順2 - 「詳細フィルター」ウィンドウと適用されたレポート指標を指すサイト合計を示すスクリーンショット。](assets/filtering_for_metric.png)
