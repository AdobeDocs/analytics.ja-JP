---
title: ディメンションの概要
description: ディメンションの概要と Adobe Analytics での使用方法について説明します。
feature: Dimensions
exl-id: dc00e06a-fdb5-40e3-82e2-269bad3b3677
TQID: https://experienceleague.adobe.com/WypIneraYlrSyIpXv3UQWIFn42A-Dxi0SxeJ2VbeubQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 436
ht-degree: 37%

---

# ディメンションの概要

ディメンションは、通常文字列値を含む、Adobe Analytics の変数です。 一般的なディメンションには、[ページ](page.md)、[参照ドメイン](referring-domain.md)、[eVar](evar.md) があります。 一方、[指標](../metrics/overview.md)には、ディメンションに結び付く数値が含まれます。 基本レポートは、文字列値（ディメンション）の行と数値（指標）の列を示します。

例えば、**[!UICONTROL ページ]**&#x200B;ディメンションと&#x200B;**[!UICONTROL 訪問回数]**&#x200B;指標を組み合わせると、最も訪問されたページを示すランクレポートが表示されます。

| ページ | 訪問回数 |
| --- | ---: |
| ホームページ | 800 |
| 製品ページ | 500 |
| 購入ページ | 100 |

{style="table-layout:fixed"}

各ディメンションは、サイトの異なる部分またはファセットを表します。 これらのディメンションのうち 1 つ以上を 1 つ以上の指標と組み合わせて、必要なレポートを作成できます。

## ディメンションの説明の追加

Analytics 管理者は、レポートスイート内または直接 Analysis Workspace 内で、ディメンションやその他のコンポーネントの説明を追加できます。 ディメンションに説明を追加する方法について詳しくは、[コンポーネントの説明の追加](/help/analyze/analysis-workspace/components/add-component-descriptions.md)を参照してください。

## 廃止されたディメンション

次のディメンションは廃止されました。 そのほとんどは、Analysis Workspaceで利用できないReports &amp; Analytics レポートです。 レガシーレポートや過去のデータで発生した場合は、参照のために、ここに文書化されています。

* **階層**: レポート用にサイトの階層構造をキャプチャするために使用されるカスタムディメンション （`hier1`-`hier5`）。 この機能は廃止され、Analysis Workspaceでは使用できません。 代わりに[eVars](evar.md)と分類を使用してください。
* **ホームページ**：現在のページが訪問者のブラウザーのホームページであるかどうかを示すフラグ。 これは、最新のブラウザープライバシー慣行に対応していない、レガシーディメンションです。
* **JavaScript サポート**：訪問者のブラウザーがJavaScriptをサポートしているかどうかを示します。 もはや現代の測定には意味のないレガシーディメンション。
* **JavaScript バージョン**：訪問者のブラウザーがサポートしているJavaScript バージョンを報告しました。 収集されなくなったレガシーディメンション。
* **次ページ**：訪問者が表示した次のページを示すパスディメンション。 現在のパスディメンションには、Analysis Workspaceの[&#x200B; フロービジュアライゼーション &#x200B;](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)を使用します。
* **前のページ**：訪問者が閲覧した前のページを表示するパスディメンション。 現在のパスディメンションには、Analysis Workspaceの[&#x200B; フロービジュアライゼーション &#x200B;](/help/analyze/analysis-workspace/visualizations/c-flow/flow.md)を使用します。
* **タイムゾーン**：訪問者のタイムゾーン。AppMeasurement イメージリクエストのタイムスタンプオフセットから派生します。 Web SDKは、[`placeContext`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/configure/context)を使用してタイムゾーンを収集します。
* **トップレベルドメイン**：訪問者のアクセスポイントのトップレベルドメイン。 従来のReports &amp; Analytics レポート。代わりに[Domain](domain.md) ディメンションを使用してください。
* **訪問ページ番号**：訪問中のページ番号。 従来のReports &amp; Analytics レポート。代わりに[&#x200B; ヒット深度](hit-depth.md) ディメンションを使用します。
* **訪問者の状態**: `s.state`変数から米国の状態を報告しました。 これは、ジオセグメンテーションを使用する[US States](us-states.md) ディメンションを支持して廃止されました。
