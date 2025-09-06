---
description: 計算指標の作成方法を説明します。
title: 計算指標の作成
feature: Calculated Metrics
exl-id: b3380d6b-53b5-40af-8e23-34772d79ae26
source-git-commit: 665319bdfc4c1599292c2e7aea45622d77a291a7
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 21%

---

# 計算指標の作成

デフォルトでは、計算指標を作成できるのは管理者のみです。 ユーザーには、他のコンポーネント（セグメント、注釈など）の表示方法と同様に、計算指標を表示する権限があります。

計算指標は次の方法で作成できます。

![ 指標の作成方法 ](assets/create-metric.png)

* **A**。メインインターフェイスで「**[!UICONTROL コンポーネント]**」を選択し、「**[!UICONTROL 計算指標]**」を選択します。 ![ 計算指標 ](/help/assets/icons/AddCircle.svg) マネージャー [!UICONTROL **[!UICONTROL &#x200B; から「]**]AddCircle[Add](cm-manager.md)」を選択します。
* **B**。Workspace プロジェクトの左側のコンポーネント パネルで、「![ イベント ](/help/assets/icons/Add.svg) ![ 指標 ](/help/assets/icons/Event.svg)」の「**追加**」を選択します。
* **C**。Workspace プロジェクトの指標列ヘッダーのコンテキストメニューで、「**[!UICONTROL 選択から指標を作成]**」を選択します。 サブメニューから、関数を選択するか、「**[!UICONTROL 計算指標ビルダーで開く]**」を選択できます。 <br/> 関数を選択すると、計算指標はプロジェクトのみの指標として定義されます。 後でこの指標を編集する際に、[ コンポーネント情報 ](/help/analyze/analysis-workspace/components/use-components-in-workspace.md) ポップアップを通じて、[ 計算指標ビルダー ](c-build-metrics/cm-build-metrics.md) に通知が表示されます。
* **D**。Workspace プロジェクトで、メニューから **[!UICONTROL コンポーネント]** を選択し、**[!UICONTROL 指標を作成]** を選択します。
* **E**. Workspace プロジェクトで、ショートカットキー **[!UICONTROL shift+cmd+c]** （macOS）または **[!UICONTROL shift+ctrl+c]** （Windows）を使用します。

新しい計算指標を定義するには、[ 計算指標ビルダー ](c-build-metrics/cm-build-metrics.md) を使用します。


## ワークフロー

計算指標を作成する前に、次のワークフローを慎重に検討してください。

| ワークフロータスク | 説明 |
| --- | --- |
| 計算指標の計画 | 特に、正式に承認される予定の指標については、どの計算指標が広く使用され、どのように定義されるかを概要で説明することは、計画を立てる上で理にかなっています。 |
| 計算指標の [ 作成 ](c-build-metrics/cm-build-metrics.md) | [!DNL Analytics] コンポーネントで使用するために、計算指標と高度な計算指標を作成および編集します。計算指標の作成方法については、[例](c-build-metrics/cm-build-metrics.md)を参照してください。 |
| [ タグ付け ](cm-tagging.md) 計算指標 | 整理および共有が容易に行えるように計算指標にタグを付けます。簡易検索および詳細検索と整理について詳しくは、タグの計画および割り当て方法に関する説明を参照してください。 |
| [ 承認 ](cm-approving.md) 計算指標 | 計算指標を正規の指標として承認します。 |
| 計算指標の使用 | プロジェクトで計算指標を使用します。 |
| [ 共有 ](cm-sharing.md) 計算指標 | 他の個人、グループまたは組織と計算指標を共有します。 |
| [ フィルター ](cm-filter.md) 計算指標 | タグ、所有者、その他のフィルターで計算指標をフィルタリングします（「すべて表示」、「自分が所有」、「自分と共有」、「お気に入り」、「承認済み」を選択）。 |
| 計算指標を [ お気に入り ](cm-finding.md) としてマーク | 指標を使いやすく整理するための 1 つの方法として、指標をお気に入りに登録することができます。 |
