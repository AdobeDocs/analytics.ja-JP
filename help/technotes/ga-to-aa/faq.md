---
title: Adobe Analytics への移行に関するよくある質問（FAQ）
description: サードパーティプラットフォームからアドビ製品への移行について、よく寄せられる質問にお答えします。
feature: Third-party Integration
exl-id: 1201909e-b20c-48c5-b287-393da8e22d78
TQID: https://experienceleague.adobe.com/NJPnGHUG-9krAfzRZiNbMd7DS9q5gRGTm-1KM3DMXag
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: e38cbddc-1633-4cd5-bed5-9f289f2a6029
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 418
ht-degree: 54%

---

# Adobe Analytics への移行に関するよくある質問（FAQ）

**サードパーティプラットフォームから Adobe Analytics に履歴データを移行するにはどうすればよいですか？**

データの収集、処理および保存の方法は、分析プラットフォームごとに異なります。 アドビでは、履歴データを移行するのではなく、Adobe Analytics 内でデータの収集と使用を開始する際に明確な切り替え日を設定することを推奨しています。 多くの場合、会計年度の初日、暦年の初日、暦月の初日が切り替え日に設定されます。 履歴データを表示するには、サードパーティプラットフォームにログインして、適切な履歴レポートを取得します。

過去のデータをAdobe Adobeに引き継ぐ場合は、Adobeのアカウントチームにお問い合わせください。 導入コンサルタントは貴社のご協力のもと、Google Analytics からデータを書き出し、アドビのデータ収集サーバーが取り込むことのできるデータソースに変換します。

過去のデータを移動する場合は、任意のオムニチャネルデータソースを取り込むことができる[Customer Journey Analytics](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-overview)を使用することをお勧めします。

**多くのレポートでは、セグメント化ドロップダウンリストに慣れています。 [!UICONTROL Analysis Workspace] でドロップダウンを再度作成する方法を教えてください。**

ドロップダウンフィルターは、[!UICONTROL Analysis Workspace]の柔軟で堅牢な機能で、セグメント化ドロップダウンリストを使用できます。 ワークスペースプロジェクト内の場合：

1. ドロップダウンフィルターに含めるコンポーネントに対して、***ctrl***+***click*** （Windows）または&#x200B;***cmd***+***click*** （Mac）を使用します。 セグメントに限定されません。 任意のコンポーネントをドロップダウンフィルターに含めることができます。
2. コンポーネントのグループを、*ここにセグメントをドロップ*&#x200B;というラベルの付いたワークスペース領域にドラッグします。 手放す前に、**[!UICONTROL shift]**&#x200B;を押し続けます。

この[!UICONTROL Workspace] プロジェクトにアクセスするユーザーは、このドロップダウンフィルターを使用して、セグメントやその他のコンポーネントをプロジェクトに適用できるようになりました。 詳しくは、『Adobe Analytics ツールガイド』の「[パネルの概要](/help/analyze/analysis-workspace/c-panels/panels.md)」を参照してください。

**ディメンション項目をクリックしてドリルダウンを表示しています。 Analysis Workspace でこのワークフローを再現する方法を教えてください。**

また、[!UICONTROL Analysis Workspace] のディメンション項目は、分類の作業が容易になります。 ディメンション項目のコンテキストメニューを使用して、分類にアクセスします。 次に、**[!UICONTROL 分類]**、および目的のコンポーネントを選択します。 各値に&#x200B;***ctrl***+***select*** （Windows）または&#x200B;***cmd***+***select*** （Mac）を使用すると、複数のディメンション項目に同じ分類を適用できます。
