---
description: Analysis Workspace とセグメントビルダーで使用可能です。
title: Experience Cloud ID を持つ訪問者
uuid: 47ebd3d6-a921-4e51-ac7a-b8d5fb9565e0
translation-type: tm+mt
source-git-commit: 3fe3442eae1bdd8b90acffc9c25d184714613c16

---


# Experience Cloud ID を持つ訪問者

Analysis Workspace とセグメントビルダーで使用可能です。

Experience Cloud ID を持つ訪問者の数を示します。どのページに ID サービスがデプロイされているかを把握でき、他の Experience Cloud ソリューションと共有できる訪問者の数を把握できます。また、この Experience Cloud に共有されるセグメントでこの指標を使用することもできます。

>[!IMPORTANT]
>
>この指標を表示するには、レポートスイートで [ID サービス](https://docs.adobe.com/content/help/ja-JP/id-service/using/home.html)を実行している必要があります。

## Experience Cloud ID 設定のデバッグ {#section_679E62142A3E46548FF8FBDA46568005}

この指 [!UICONTROL Visitors with Experience Cloud ID] 標は、設定の検索とデバッグを行うのに役立つAdobe Analyticsの指標 [!UICONTROL Identity Service]です。 この指標は、レポートスイートの訪問者のうち、ID サービスから Experience Cloud ID を割り当てられている訪問者の数です。この指標は、特定の Experience Cloud 統合が想定どおりの数の訪問者を共有していない可能性がある場合にその原因を診断したり、MCID がまだ導入されていない可能性のあるサイト領域を特定したりするうえで、非常に役に立ちます。

To use the Visitors with Experience Cloud ID metric, simply drag it in to any report as a metric, such as this [!UICONTROL Pages] report:

![](assets/metric-mcvid1.png)

この例では、各ページの実訪問者数が Experience Cloud ID での訪問者と同じ数になっていることに注意してください。ただし、実訪問者数の合計数は Experience Cloud ID での訪問者の合計数より大きくなっています。まだすべての訪問者に MCID を設定していないページを見つけるには、次のような定義の[計算指標を作成](https://docs.adobe.com/content/help/ja-JP/analytics/components/calculated-metrics/calcmetric-workflow/cm-build-metrics.html)します。

![](assets/metric-mcvid2.png)

この計算指標をレポートに追加することで、MCID を持たない訪問者の数が最も多いページがひとめでわかるように、ページレポートをソートすることができます。

![](assets/metric-mcvid3.png)

これで、「Product Quick Views」ページに ID サービスが適切に実装されておらず、このページをできるだけ早く更新する必要があることがすぐにわかります。ブラウザーのタイプ、サイトセクション、コンテンツタイプなど、任意のタイプのディメンションに基づいて、同様のレポートを作成することができます。

MCID を持たない訪問者がいるページを特定したら、その情報を実装チームにフィードバックして、それらのページを修正してもらうことができます。

場合によっては、MCID サービスがページに実装されていても一部の訪問者に MCID が設定されていないこともあります。そのような場合、原因として最も可能性が高いのは、Analytics JavaScript または DTM のよくある設定ミスで、レポートスイートが用意される前に AppMeasurement 関数が呼び出されることです。これを避けるには、適切に[コア AppMeasurement コードを挿入](https://docs.adobe.com/content/help/en/analytics/implementation/other/dtm/analytics-tool/t-appmeasurement-code.html)します。

上記の「Product Quick Views」ページに基づくセグメントのうち、Experience Cloud と共有しているものはすべて、他の Experience Cloud ソリューションとの一致率が非常に低くなる可能性が高いことに注意してください。任意のセグメントの MCID 適用範囲を確認するには、次のようなレポートを作成します。

![](assets/metric-mcvid4.png)

このテーブルでは実訪問者数と Experience Cloud ID での訪問者の数を比較していますが、これを見ると、「セグメント 1」の MCID 適用範囲が 100％でないのに対して、「セグメント 2」の場合は 100％になっていることが容易にわかります。つまり、セグメント 1 を Experience Cloud と共有しても、合計 3,859 人の訪問者のうち 2,186 人しか共有対象にならないということです。
