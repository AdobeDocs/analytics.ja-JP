---
description: Analysis Workspace 内で、コンテキスト上のデータの異常値を表示および分析できます。
title: 異常値検出の概要
uuid: 991fde08-198c-4410-9606-d5a4f3dd8339
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# 異常値検出の概要

Analysis Workspace 内で、コンテキスト上のデータの異常値を表示および分析できます。

[異常値検出（YouTube）](https://www.youtube.com/watch?v=krXyQCjXoeU&amp;index=63&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)（4:53）

[貢献度分析（YouTube）](https://www.youtube.com/watch?v=MbpeJIADtGk&amp;index=64&amp;list=PL2tCx83mn7GuNnQdYGOtlyCu0V5mEZ8sS)（3:20）

>[!IMPORTANT]異常値検出は、Reports &amp; Analytics の画面から削除され、現在は、Analysis Workspace からのみ使用できます。Adobe Analytics Select および Adobe Analytics Foundation をご利用のお客様は、Workspace で「毎日の精度」の異常値検出のみにアクセスできます。詳しくは、[異常値検出と貢献度分析の権限](/help/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.md#section_9278D58F21A840AA9B1ED1BD07A1EF0A)を参照してください。

異常値検出は、以前のデータに関連して特定の指標がどのように変化したかを判定するための統計的手法です。

異常値検出により、「ノイズ」から「真のシグナル」を分離し、これらのシグナルまたは異常値の潜在的な要因を特定できます。つまり、変則性の検出を使用すると、重要な統計変動と重要でない統計変動を識別できます。さらに、信頼できる指標（KPI）の予測を取得できます。

調査できる異常値の例を次に示します。

* 平均注文額の急激な下落
* 売上の低い注文の急増
* トライアル登録の急増または下落
* ランディングページ表示の下落
* ビデオバッファーイベントの急増
* ビデオの低ビットレートの下落

異常値検出と[貢献度分析](https://marketing.adobe.com/resources/help/ja_JP/analytics/contribution/ca_main.html)の双方が、Analysis Workspace の主要ワークフローです。毎日の異常値に対して貢献度分析を実行し、Analysis Workspace プロジェクトに結果を埋め込むことができます。

Analysis Workspace の異常値検出アルゴリズムには以下が含まれています。

* 既存の毎日の精度に加えて、1 時間ごと、毎週および毎月の精度のサポート
* シーズナリティ（「ブラックフライデー」など）や休日の認識
