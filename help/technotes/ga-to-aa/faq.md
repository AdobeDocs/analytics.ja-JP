---
title: Adobe Analytics への移行に関するよくある質問（FAQ）
description: サードパーティプラットフォームからアドビ製品への移行について、よく寄せられる質問にお答えします。
feature: Third-party Integration
exl-id: 1201909e-b20c-48c5-b287-393da8e22d78
source-git-commit: 58d53d6013abcd7d99f2c3cb640d6a648a4ef360
workflow-type: tm+mt
source-wordcount: '396'
ht-degree: 53%

---

# Adobe Analytics への移行に関するよくある質問（FAQ）

**サードパーティプラットフォームから Adobe Analytics に履歴データを移行するにはどうすればよいですか？**

データの収集、処理および保存の方法は、分析プラットフォームごとに異なります。アドビでは、履歴データを移行するのではなく、Adobe Analytics 内でデータの収集と使用を開始する際に明確な切り替え日を設定することを推奨しています。多くの場合、会計年度の初日、暦年の初日、暦月の初日が切り替え日に設定されます。履歴データを表示するには、サードパーティプラットフォームにログインして、適切な履歴レポートを取得します。

履歴データをAdobeに移植することにこだわる場合は、Adobe アカウントチームにお問い合わせください。 導入コンサルタントは貴社のご協力のもと、Google Analytics からデータを書き出し、アドビのデータ収集サーバーが取り込むことのできるデータソースに変換します。

履歴データの移動には、[Customer Journey Analyticsを使用することをお勧めします。これにより ](https://experienceleague.adobe.com/ja/docs/analytics-platform/using/cja-overview/cja-overview) 任意のオムニチャネルデータソースを取り込むことができます。

**多くのレポートで「セグメント化」ドロップダウンリストを使用しています。 [!UICONTROL Analysis Workspace] でドロップダウンを再度作成する方法を教えてください。**

ドロップダウンフィルターは、[!UICONTROL Analysis Workspace] の柔軟で堅牢な機能で、セグメント化ドロップダウンリストを使用できます。 ワークスペースプロジェクト内の場合：

1. ドロップダウンフィルターに含めるコンポーネントで、***ctrl***+***クリック*** （Windows）または ***cmd***+***クリック*** （Mac）を使用します。 セグメントに限定されません。 任意のコンポーネントをドロップダウンフィルターに含めることができます。
2. コンポーネントのグループを「*セグメントをここにドロップ*」というラベルが付いたワークスペース領域にドラッグします。 手放す前に、**[!UICONTROL shift]** キーを押したままにします。

この [!UICONTROL Workspace] プロジェクトにアクセスするユーザーは、このドロップダウンフィルターを使用して、セグメントまたは他のコンポーネントをプロジェクトに適用できるようになりました。 詳しくは、『Adobe Analytics ツールガイド』の「[パネルの概要](/help/analyze/analysis-workspace/c-panels/panels.md)」を参照してください。

**ディメンション項目をクリックしてドリルダウンを表示しています。Analysis Workspace でこのワークフローを再現する方法を教えてください。**

また、[!UICONTROL Analysis Workspace] のディメンション項目は、分類の作業が容易になります。ディメンション項目のコンテキストメニューを使用して分類にアクセスします。 次に、**[!UICONTROL 分類]** を選択し、目的のコンポーネントを選択します。 各値に対して ***ctrl***+***select*** （Windows）または ***cmd***+***select*** （Mac）を使用することで、複数のディメンション項目に同じ分類を適用できます。
