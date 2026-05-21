---
description: 計算指標の作成方法を説明します。
title: 計算指標の作成
feature: Calculated Metrics
exl-id: b3380d6b-53b5-40af-8e23-34772d79ae26
TQID: https://experienceleague.adobe.com/KuWD2kus9wcFW7yULWbLwfj4hfVHJgTjDeCJzEWwKFU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 367
ht-degree: 15%

---

# 計算指標の作成

デフォルトでは、計算指標を作成できるのは管理者のみです。 ユーザーには、他のコンポーネント（セグメント、注釈など）を表示する方法と同様に、計算指標を表示する権限があります。

計算指標は、次の方法で作成できます。

![指標を作成する方法](assets/create-metric.png)

* **A**。メインインターフェイスで、**[!UICONTROL コンポーネント]**&#x200B;を選択し、**[!UICONTROL 計算指標]**&#x200B;を選択します。 [[!UICONTROL 計算指標] マネージャー](cm-manager.md)から![AddCircle](/help/assets/icons/AddCircle.svg) [!UICONTROL **[!UICONTROL Add]**]を選択します。
* **B**。Workspace プロジェクトで、「コンポーネント」左パネルから、![&#x200B; イベント &#x200B;](/help/assets/icons/Event.svg) **指標**&#x200B;の![追加](/help/assets/icons/Add.svg)を選択します。
* **C**。Workspace プロジェクトで、メトリクス列ヘッダーのコンテキストメニューから「**[!UICONTROL 選択範囲からメトリクスを作成]**」を選択します。 サブメニューから、関数を選択するか、計算指標ビルダーで&#x200B;**[!UICONTROL 開く]**&#x200B;を選択できます。 <br/>関数を選択すると、計算指標はプロジェクトのみの指標として定義されます。 後でこの指標を編集すると、[&#x200B; コンポーネント情報](/help/analyze/analysis-workspace/components/use-components-in-workspace.md) ポップアップを使用して、[計算指標ビルダー](c-build-metrics/cm-build-metrics.md)に通知が表示されます。
* **D**。Workspace プロジェクトで、メニューから「**[!UICONTROL コンポーネント]**」を選択し、「**[!UICONTROL 指標を作成]**」を選択します。
* **E**。Workspace プロジェクトでは、ショートカット **[!UICONTROL shift+cmd+c]** （macOS）または&#x200B;**[!UICONTROL shift+ctrl+c]** （Windows）を使用します。

新しい計算指標を定義するには、[計算指標ビルダー](c-build-metrics/cm-build-metrics.md)を使用します。


## ワークフロー

計算指標を作成する前に、次のワークフローを慎重に検討してください。

| ワークフロータスク | 説明 |
| --- | --- |
| 計算指標の計画 | 特に、正式に承認される指標の場合、どの計算指標を広く使用し、どのように定義するかを概説することは合理的です。 |
| [&#x200B; ビルド &#x200B;](c-build-metrics/cm-build-metrics.md)計算指標 | [!DNL Analytics] コンポーネントで使用するために、計算指標と高度な計算指標を作成および編集します。  計算指標の作成方法については、[例](c-build-metrics/cm-build-metrics.md)を参照してください。 |
| [&#x200B; タグ &#x200B;](cm-tagging.md)計算指標 | 計算指標にタグを付けて、容易に整理および共有。 簡易検索および詳細検索と整理について詳しくは、タグの計画および割り当て方法に関する説明を参照してください。 |
| [計算指標の承認](cm-approving.md) | 計算された指標を承認し、規範的なものにします。 |
| 計算指標の使用 | プロジェクトで計算指標を使用します。 |
| [計算指標を共有](cm-sharing.md)する | 計算指標を他の個人、グループ、組織と共有します。 |
| [&#x200B; フィルター](cm-filter.md)計算指標 | タグ、所有者、その他のフィルター（すべて表示、自分、自分と共有、お気に入り、承認済み）で計算指標をフィルタリングします。 |
| 計算指標をお気に入り[としてマーク &#x200B;](cm-finding.md) | 指標を使いやすく整理するための 1 つの方法として、指標をお気に入りに登録することができます。 |
