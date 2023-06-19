---
title: Adobe Analytics マーケティングチャネルの実装のベストプラクティス
description: マーケティングチャネルでの Attribution IQ と Customer Journey Analytics の使用に関するベストプラクティスの更新
feature: Marketing Channels
exl-id: a0ab818d-7165-4f34-bc43-1ed8d6215800
source-git-commit: 15f1cd260709c2ab82d56a545494c31ad86d0ab0
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Attribution IQ とマーケティングチャネル — ベストプラクティス

[マーケティングチャネル](/help/components/c-marketing-channels/c-getting-started-mchannel.md)は、Adobe Analytics の貴重で強力な機能です。マーケティングチャネルの実装に関する現在のガイダンスは、[Attribution IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html#analysis-workspace) も [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/marketing-channels.html?lang=ja#cja-usecases) も存在しなかったときに作成されています。

マーケティングチャネルの実装を将来的に実証し、Attribution IQ や Customer Journey Analytics との一貫性をレポートに確実に保つために、一連の更新されたベストプラクティスを発行しています。既にマーケティングチャネルを使用している場合は、これらの新しいガイドラインの中から最適なオプションを選択できます。マーケティングチャネルを初めて使用する場合は、すべての新しいベストプラクティスに従うことをお勧めします。

マーケティングチャネルが初めて導入された際にあったディメンションはファーストタッチとラストタッチのみでした。現在のバージョンのアトリビューションでは、明示的なファーストタッチディメンションとラストタッチディメンションは不要になりました。アドビでは、汎用の「マーケティングチャネル」ディメンションと「マーケティングチャネルの詳細」ディメンションを提供し、それらを目的のアトリビューションモデルで使用できるようにしています。これらの汎用ディメンションは、「ラストタッチチャネル」ディメンションと同じように動作しますが、異なるアトリビューションモデルでマーケティングチャネルを使用する場合の混乱を防ぐために、異なるラベルが付けられます。

マーケティングチャネルのディメンションは、（処理ルールで定義された）従来の訪問の定義に依存するので、仮想レポートスイートを使用して訪問の定義を変更することはできません。これらの修正されたプラクティスにより、Attribution IQと Customer Journey Analytics を使用した、明確で制御可能なルックバックウィンドウが有効になります。

## ベストプラクティス #1：Attribution IQ を制御分析に活用

マーケティングチャネル分析を微調整するには、既存のマーケティングチャネルアトリビューションの代わりに [Attribution IQ](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/overview.html#analysis-workspace) を使用することをお勧めします。他のベストプラクティスに従って、Attribution IQ を使用した分析との一貫性と堅牢な制御を確保します。

![](assets/attribution.png)

* 「マーケティングチャネル」と「マーケティングチャネルの詳細」ディメンションの設定では、各マーケティングチャネルインスタンスに対応する、評価対象タッチポイントを設定します。
* 指標分析の場合、組織は 1 つ以上のアトリビューションモデルに合わせる必要があります。再利用しやすいように、カスタム指標をこのモデルと共に保存します。
* デフォルトでは、データはラストタッチと訪問者エンゲージメント期間の設定を使用して割り当てられます。Attribution IQ 指標モデルは、ルックバックウィンドウの制御を強化し、[アルゴリズムのアトリビューション](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/algorithmic.html#analysis-workspace)を含む多様性を提供します。

## ベストプラクティス #2：「直接」および「セッション更新」チャネル定義がない

「直接」および「内部／セッション更新」チャネルをカスタムアトリビューションモデル（Attribution IQ）で使用することはお勧めしません。

組織で「直接」および「セッション更新」が既に設定されている場合は、この場合、ファーストタッチ/ラストタッチの[分類を作成](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/classifications-mchannel.md)し、ダイレクトチャネルとセッション更新チャネルを未分類のままにすることをお勧めします。分類されたディメンションは、これらのチャネルが設定されていない場合と同じ Attribution IQ 結果を生成します。

![](assets/direct-session-refresh.png)

## ベストプラクティス #3：すべてのチャネルに対してラストタッチチャネルの上書きを有効にする

Workspace のマーケティングチャネルディメンションで使用されるカスタムアトリビューションモデルは、この設定が有効な場合に最も適しています。この設定を有効にすると、新しいチャネル／詳細が見つかった場合にマーケティングチャネルインスタンスがカウントされます。「直接」と「内部／セッション更新」を除くすべてのチャネルに対してこの機能を有効にする必要があります。この 2 つをカスタムアトリビューションモデル（Attribution IQ）で使用することは推奨されなくなっています。

![](assets/override.png)

## ベストプラクティス #4：訪問者エンゲージメント期間の最小化

訪問者エンゲージメント期間を最小で「1 日」に設定すると、値が持続する可能性を最小限に抑えることができます。 カスタムアトリビューションモデル（AIQ）では柔軟なルックバックウィンドウを許可するので、この設定の影響を最小限に抑えるために、最小値を設定することをお勧めします。

![](assets/expiration.png)

## ベストプラクティス #5：マーケティングチャネルの処理ルールは有効なチャネルに対してのみ存在する

無効なチャネルに対するマーケティングチャネルの処理ルールをすべて削除してください。ルールは、有効として確認されているマーケティングチャネルに対してのみ存在する必要があります。
