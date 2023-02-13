---
title: Adobe Analytics への移行に関するよくある質問（FAQ）
description: サードパーティプラットフォームからアドビ製品への移行について、よく寄せられる質問にお答えします。
feature: Third-party Integration
exl-id: 1201909e-b20c-48c5-b287-393da8e22d78
source-git-commit: ac9e4934cee0178fb00e4201cc3444d333a74052
workflow-type: ht
source-wordcount: '397'
ht-degree: 100%

---

# Adobe Analytics への移行に関するよくある質問（FAQ）

**サードパーティプラットフォームから Adobe Analytics に履歴データを移行するにはどうすればよいですか？**

データの収集、処理および保存の方法は、分析プラットフォームごとに異なります。アドビでは、履歴データを移行するのではなく、Adobe Analytics 内でデータの収集と使用を開始する際に明確な切り替え日を設定することを推奨しています。多くの場合、会計年度の初日、暦年の初日、暦月の初日が切り替え日に設定されます。履歴データを表示するには、サードパーティプラットフォームにログインして、適切な履歴レポートを取得します。

アドビ製品への履歴データの移行をご検討の方は、担当のアカウントマネージャーにお問い合わせください。導入コンサルタントは貴社のご協力のもと、Google Analytics からデータを書き出し、アドビのデータ収集サーバーが取り込むことのできるデータソースに変換します。

履歴データの移動には、[Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=ja) を使用することをお勧めします。これにより、任意のオムニチャネルデータソースを取り込むことができます。

**多くのレポートでセグメント化ドロップダウンを使用しています。[!UICONTROL Analysis Workspace] でドロップダウンを再度作成する方法を教えてください。**

[!UICONTROL Analysis Workspace] では、堅牢かつ柔軟なドロップダウンフィルターによるセグメント化ドロップダウンを使用できます。ワークスペースプロジェクト内の場合：

1. Ctrl キー（Windows）または Command キー（Mac）を押しながら、ドロップダウンに含めるコンポーネントをクリックします。ドロップダウンフィルターには、セグメントだけでなくコンポーネントも含めることができます。
2. コンポーネントのグループを、「ここにセグメントをドロップ」というラベルの付いたワークスペース領域にドラッグします。移動させる前に、Shift キーを押し続けます。

該当する [!UICONTROL Workspace] プロジェクトへのアクセス権を持つユーザーは、このドロップダウンを使用して、セグメントや他のコンポーネントをプロジェクトに適用できるようになりました。詳しくは、『Adobe Analytics ツールガイド』の「[パネルの概要](/help/analyze/analysis-workspace/c-panels/panels.md)」を参照してください。

**ディメンション項目をクリックしてドリルダウンを表示しています。Analysis Workspace でこのワークフローを再現する方法を教えてください。**

また、[!UICONTROL Analysis Workspace] のディメンション項目は、分類の作業が容易になります。左クリックではなく右クリックでアクセスします。ディメンション項目を右クリックし「[!UICONTROL 分類]」をクリックして適切なコンポーネントを選択します。Ctrl キー（Windows）または Command キー（Mac）を押しながら各項目をクリックすると、同じ分類を複数のディメンション項目に適用できます。
