---
description: Analysis Workspace とセグメントビルダーで使用可能です。
seo-description: Analysis Workspace とセグメントビルダーで使用可能です。
seo-title: Experience Cloud ID を持つ訪問者
title: Experience Cloud ID を持つ訪問者
uuid: 47ebd3d6-a921-4e51-ac7a-b8d5fb9565e0
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Experience Cloud ID を持つ訪問者

Analysis Workspace とセグメントビルダーで使用可能です。

Experience Cloud ID を持つ訪問者の数を示します。IDサービスがデプロイされているページを把握し、他のExperience cloudソリューションと共有できる訪問者数を把握できます。 また、この Experience Cloud に共有されるセグメントでこの指標を使用することもできます。

>[!IMPORTANT]
>
>For this metric to appear, you have to have the [Identity Service](https://marketing.adobe.com/resources/help/en_US/mcvid/) running for the report suite.

## Experience Cloud ID 設定のデバッグ {#section_679E62142A3E46548FF8FBDA46568005}

The [!UICONTROL Visitors with Experience Cloud ID] metric is a useful metric in Adobe Analytics intended to help you find and debug your [!UICONTROL Identity Service]setup. この指標は、IDサービスからExperience Cloud IDが割り当てられた、レポートスイート内の訪問者数のカウントです。 この指標は、特定の Experience Cloud 統合が想定どおりの数の訪問者を共有していない可能性がある場合にその原因を診断したり、MCID がまだ導入されていない可能性のあるサイト領域を特定したりするうえで、非常に役に立ちます。

「Experience Cloud ID での訪問者」指標を使用するには、次の[!UICONTROL ページ]レポートのような任意のレポートに指標としてドラッグするだけです。

![](assets/metric-mcvid1.png)

この例では、各ページの実訪問者数が Experience Cloud ID での訪問者と同じ数になっていることに注意してください。ただし、実訪問者数の合計数は Experience Cloud ID での訪問者の合計数より大きくなっています。まだすべての訪問者に MCID を設定していないページを見つけるには、次のような定義の[計算指標を作成](https://marketing.adobe.com/resources/help/en_US/analytics/calcmetrics/cm_build_metrics.html)します。

![](assets/metric-mcvid2.png)

この計算指標をレポートに追加することで、MCID を持たない訪問者の数が最も多いページがひとめでわかるように、ページレポートをソートすることができます。

![](assets/metric-mcvid3.png)

これで、「製品のクイックビュー」ページがIDサービスで適切に実装されておらず、できるだけ早く更新する必要があることがすぐにわかります。 ブラウザーのタイプ、サイトセクション、コンテンツタイプなど、任意のタイプのディメンションに基づいて、同様のレポートを作成することができます。

MCIDを持たない訪問者がいるページを特定したら、導入チームにそのページを返して、それらのページを修正できるようにする必要があります。

場合によっては、MCID サービスがページに実装されていても一部の訪問者に MCID が設定されていないこともあります。そのような場合、原因として最も可能性が高いのは、Analytics JavaScript または DTM のよくある設定ミスで、レポートスイートが用意される前に AppMeasurement 関数が呼び出されることです。これを避けるには、適切に[コア AppMeasurement コードを挿入](https://marketing.adobe.com/resources/help/en_US/sc/implement/dtm/t_appmeasurement-code.html)します。

Experience cloudと共有する「製品のクイックビュー」ページ（上図を参照）に基づくセグメントは、他のExperience cloudソリューションとの比較率が非常に低い可能性があります。 任意のセグメントの MCID 適用範囲を確認するには、次のようなレポートを作成します。

![](assets/metric-mcvid4.png)

この表では、訪問者に対する個別訪問者数とExperience Cloud IDを比較していますが、「セグメント1」は100% MCIDの範囲を持たず、「セグメント2」は100% MCIDの範囲を持たないのが簡単にわかります。 つまり、セグメント 1 を Experience Cloud と共有しても、合計 3,859 人の訪問者のうち 2,186 人しか共有対象にならないということです。
