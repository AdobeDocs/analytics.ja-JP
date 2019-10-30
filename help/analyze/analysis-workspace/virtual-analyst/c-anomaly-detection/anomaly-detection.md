---
description: Analysis Workspace 内で、コンテキスト上のデータの異常値を表示および分析できます。
seo-description: Analysis Workspace 内で、コンテキスト上のデータの異常値を表示および分析できます。
seo-title: 異常値検出の概要
title: 異常値検出の概要
uuid: 991fde08-198c-4410-9606-d5a4f3dd8339
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 異常値検出の概要

Analysis Workspace内でコンテキスト上のデータの異常を表示および分析できます。

[YouTubeでの異常値検出](https://www.youtube.com/watch?v=krXyQCjXoeU&index=63&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (4:53)

[YouTubeでの貢献度分析](https://www.youtube.com/watch?v=MbpeJIADtGk&index=64&list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS) (3:20)

> [!IMPORTANT] 異常値検出は、Analysis Workspaceでのみ使用できます。 Adobe Analytics Select and Foundationのお客様は、Workspaceの「毎日の精度」の異常値検出にのみアクセスできます。 詳しくは、[異常値検出と貢献度分析の権限](../contribution-analysis/ca-tokens.md)を参照してください。

異常値検出は、以前のデータに関連して特定の指標がどのように変化したかを判定するための統計的手法です。

異常値検出により、「ノイズ」から「真のシグナル」を分離し、これらのシグナルまたは異常値の潜在的な要因を特定できます。つまり、変則性の検出を使用すると、重要な統計変動と重要でな統計変動を識別できます。さらに、信頼できる指標（KPI）の予測を取得できます。

調査できる異常値の例を次に示します。

* 平均注文額の急激な下落
* 売上の低い注文の急増
* トライアル登録の急増または下落
* ランディングページ表示の下落
* ビデオバッファーイベントの急増
* ビデオの低ビットレートの下落

異常値検出と[貢献度分析](https://marketing.adobe.com/resources/help/en_US/analytics/contribution/ca_main.html)の双方が、Analysis Workspace の主要ワークフローです。毎日の異常値に対して貢献度分析を実行し、Analysis Workspace プロジェクトに結果を埋め込むことができます。

Analysis Workspace の異常値検出アルゴリズムには以下が含まれています。

* 既存の毎日の精度に加えて、1 時間ごと、毎週および毎月の精度のサポート
* シーズナリティ（「ブラックフライデー」など）や休日の認識
