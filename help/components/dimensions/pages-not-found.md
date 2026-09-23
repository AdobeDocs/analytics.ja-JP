---
title: ページが見つかりません（ディメンション）
description: サイトでエラーを返した URL。
feature: Dimensions
exl-id: 28c22565-7fcf-49f1-8876-0db88f12a182
TQID: https://experienceleague.adobe.com/0S2WzNRJrtOa9ZPTg5cmbwxMLJE5tI6Qa3GtZs6GqKc
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 54%
---
# ページが見つかりません

>[!BEGINSHADEBOX]

*このヘルプページでは、「ページが見つかりません」が [ディメンション](overview.md)として機能する方法について説明します。 指標としての機能について詳しくは、[&#x200B; ページが見つかりません](../metrics/pages-not-found.md)指標ページを参照してください。*

>[!ENDSHADEBOX]

「ページが見つかりません」ディメンションは、エラーを含む URL を示します。 このディメンションは、訪問者がサイトにたどり着くエラーの数を減らしたい場合に役立ちます。

* このディメンションを[フロービジュアライゼーション](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)で使用して、訪問者がエラーに到達するためにクリックスルーしたページを確認できます。 その後、組織の開発チームと協力して各ページのリンクを修正できます。
* このディメンションを[リファラー](referrer.md)ディメンションと共に使用して、外部リンクから訪問者がサイトに到達した場所を確認できます。 その後、目的の場所にリダイレクトを実装するか、サードパーティと協力してリンクを修正します。

>[!NOTE]
>
>Data Warehouseでは、このディメンションの名前は&#39;[!UICONTROL Page Type Error]&#39;です。

## このディメンションへのデータ入力

AppMeasurement は、[`pageType`](/help/implement/vars/page-vars/pagetype.md) 変数を使用してこのデータを収集します。 `pageType`が`errorPage`に設定されている場合、ヒットのページ URLはディメンション項目として記録されます。 `pageType`変数が定義されていないか、他の値に設定されている場合、このディメンションのデータは収集されません。

| プロパティ | 値 |
| --- | --- |
| **AppMeasurement変数** | [`pageType`](/help/implement/vars/page-vars/pagetype.md) |
| **Web SDK / XDM フィールド** | [`web.webPageDetails.isErrorPage`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-types/webpage-details) |
| **クエリパラメーター** | [`pageType`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **XML タグ** | [`<pageType>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **バイト制限** | 該当なし |
| **永続性** | ヒット |

## ディメンション項目

ディメンション項目には、エラーが発生したサイト上のページの URL が含まれます。
