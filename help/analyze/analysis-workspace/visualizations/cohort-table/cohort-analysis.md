---
title: コホート分析の概要と仕組み
description: オーディエンスに関するデータをより深く掘り下げ、コホート分析を使用して関連グループに分類します。 Analysis Workspace のコホート分析について説明します。
feature: Cohort Analysis
role: User, Admin
exl-id: 6a46e76f-671e-4b1b-933a-6c2776c72d09
source-git-commit: c0855c6bed6a9762c0440e1a8e004ee11020808e
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 93%

---

# コホートテーブルの概要 {#cohort-table-overview}


<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_button"
>title="コホートテーブル"
>abstract="コホートビジュアライゼーションを作成して、イベントの完了に基づいてユーザーをグループ化し、進行中のエンゲージメントと時間の経過に伴うチャーンを分析します。"

<!-- markdownlint-enable MD034 -->

<!-- markdownlint-disable MD034 -->

>[!CONTEXTUALHELP]
>id="workspace_cohorttable_panel"
>title="コホートテーブル"
>abstract="イベントの完了に基づいてユーザーをグループ化し、進行中のエンゲージメントとチャーンの推移を分析します。<br/><br/>**パラメーター&#x200B;**<br/>**インクルージョン条件**：最初の訪問者コホートの定義に使用するコンポーネント。<br/>**再来訪条件**：訪問者が再来訪したかどうかを判断するために使用するコンポーネント。"

<!-- markdownlint-enable MD034 -->


>[!BEGINSHADEBOX]

*この記事は、**Adobe Analyticsのコホートテーブルに関するドキュメントです**。<br/> この記事の&#x200B;**Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-workspace/visualizations/cohort-table/cohort-analysis) バージョンについては、[ コホートテーブル**を参照してください。*

>[!ENDSHADEBOX]

*`cohort`* とは、特定の期間、共通の特性を共有する人々のグループのことです。[!UICONTROL コホート分析は]、例えば、コホートがブランドとどのように関わっているかを学ぶ場合に便利です。トレンドの変更を簡単に見分けて、それに応じて対応できます（[!UICONTROL コホート分析]の説明は、[コホート分析 101](https://ja.wikipedia.org/wiki/Cohort_analysis) など、Web 上で参照できます）。

コホートレポートを作成したら、コンポーネント（特定のディメンション、指標およびセグメント）をキュレートして、任意のユーザーとコホートレポートを共有できます。[キュレートおよび共有](/help/analyze/analysis-workspace/curate-share/curate.md)を参照してください。

[!UICONTROL コホート分析]では、例えば次の操作をおこなえます。

* 目的のアクションを促進するために設計したキャンペーンを開始する。
* 顧客のライフサイクルのまさに適切なタイミングでマーケティング予算を振り替える。
* 価値を最大化するために、トライアルやオファーを終了するタイミングを認識する。
* 価格やアップグレードパスなどの領域で、A/B テストの着想を得る。

[!UICONTROL コホート分析]は、[!UICONTROL Analysis Workspace] へのアクセス権を持つすべての Adobe Analytics ユーザーが利用できます。

Analysis Workspace のコホートテーブルに関するビデオ：

>[!VIDEO](https://video.tv.adobe.com/v/25965/?quality=12)

>[!IMPORTANT]
>
>[!UICONTROL  コホート分析 ] では、セグメント化できない指標（計算指標など）、整数以外の指標（売上高など）、発生件数はサポートしていません。
>
>[!UICONTROL コホート分析] で使用できるのはセグメントで使用できる指標のみで、一度に増やせるのは 1 を超える数のみです。

## コホート分析の機能

次の機能を使用すると、作成するコホートを細かく制御できます。

### [!UICONTROL リテンションテ]ーブル

[!UICONTROL リテンション]コホートレポートが訪問者を返す：各データセルは、その期間にアクションをおこなったコホートの生の訪問者数と割合を表します。指標は最大 3 個、セグメントは最大 10 個含めることができます。

![](assets/retention-report.png)

ローリングリテンションの計算に関するビデオを次に示します。

>[!VIDEO](https://video.tv.adobe.com/v/25962/?quality=12)

### [!UICONTROL チャーンテーブル]

[!UICONTROL チャーン]コホートはリテンションテーブルの逆で、コホートにおいてフォールアウトした訪問者、または一定期間内にリターン条件を満たしていない訪問者が表示されます。指標は最大 3 個、セグメントは最大 10 個含めることができます。

![](assets/churn-report.png)

チャーン分析に関するビデオを次に示します。

>[!VIDEO](https://video.tv.adobe.com/v/25966/?quality=12)

### [!UICONTROL ローリング計算]

「含む」列ではなく、直前の列に基づいてリテンションまたはチャーンを計算できます。

![](assets/cohort-rolling-calculation.png)

### [!UICONTROL 待ち時間テーブル]

インクルージョンイベントが発生した前後の経過時間を測定します。このツールは、イベント発生前後の分析に役立ちます。「**[!UICONTROL 含む]**」列がテーブルの中央にあり、インクルージョンイベント発生の前と後の期間が両側に表示されます。

![](assets/cohort-latency.png)

### [!UICONTROL カスタムディメンショ]ンコホート

デフォルトの時間に基づくコホートではなく、選択したディメンションに基づいてコホートを作成します。[!UICONTROL マーケティングチャネル]、[!UICONTROL キャンペーン]、[!UICONTROL 製品]、[!UICONTROL ページ]、[!UICONTROL 地域]などのディメンションや、Adobe Analytics のその他のディメンションを使用して、これらのディメンションの様々な値に基づいてリテンションがどのように変化しているかを表示します。

![](assets/cohort-customizable-cohort-row.png)

コホートレポートを設定および実行する方法については、「[コホート分析レポートの設定](/help/analyze/analysis-workspace/visualizations/cohort-table/t-cohort.md)」を参照してください。
