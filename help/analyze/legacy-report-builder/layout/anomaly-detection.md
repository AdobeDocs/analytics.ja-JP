---
description: 異常値検出とその計算方法について説明します。
title: 異常値検出を使用してトレンドを自動的に見つける方法
uuid: 02da21b4-3394-471b-97b5-aa1bddf1f445
feature: Report Builder
role: User, Admin
exl-id: 6e3881c8-3e1c-4df8-ba38-e8bc84cfc3d4
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '509'
ht-degree: 91%

---

# 異常値検出{#anomaly-detection}

{{legacy-arb}}

異常値検出は、統計的なモデリングを使用して、データ内の予期しないトレンドを自動的に見つけます。モデルによって指標を分析し、値の下限、上限、予想される範囲を決定します。予期しないスパイクまたは下落が発生した場合にレポートします。

調査できる異常値の例を次に示します。

* 平均注文額の急激な下落
* 売上の低い注文の急増
* トライアル登録の急増または下落
* ランディングページ表示の下落
* ビデオのバッファーイベントの下落
* ビデオの低ビットレートの下落

>[!NOTE]
>
>異常値検出は、「日」の精度を選択した場合にのみ利用できます。

<p class="head"> <b>異常値検出の指標</b> </p>

異常値検出により、選択する各指標に次のような新しい指標が追加されます。

<table id="table_BF75FC874634498DB6632C12CBD8D533"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> 要素 </th> 
   <th colname="col2" class="entry"> 説明 </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 下限 </td> 
   <td colname="col2"> <p>予測区間の下限の水準。この水準よりも下の値は異常と見なされます。 </p> <p>値がこの水準を上回る信頼度は 95 ％です。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 期待値 </td> 
   <td colname="col2"> <p>データ分析に基づいて予測される値。この値は、下限と上限の中間点でもあります。 </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 上限 </td> 
   <td colname="col2"> <p>予測区間の上限の水準。この水準よりも上の値は異常と見なされます。 </p> <p>値がこの水準を下回る信頼度は 95 ％です。 </p> </td> 
  </tr> 
 </tbody> 
</table>

Report Builder では、選択した指標にこれらの値が適用されます。例えば、ページビュー指標を選択して異常値検出を適用した場合は、*`Page Views Lower Bound`* の指標が使用されます。

**異常値検出の計算方法**

異常値検出では、1 日あたりの予測区間データの計算、学習およびレポート作成のために、トレーニング期間が使用されます。このトレーニング期間は、通常状態と異常状態を識別し、学習したことをレポート期間に適用するための履歴的な期間です。マーケティングレポートでは、30 日、60 日および 90 日のトレーニング期間を利用できます。Report Builderでは、30 日が利用可能です。

トレーニング期間は、選択したレポート期間と同一でない場合もあります。レポートグラフには、カレンダーで指定した日付範囲の期間が表示されます。

データを計算するために、各指標の日次合計がトレーニング期間と比較されます。そのために、次のアルゴリズムが使用されます。

* ホルトウィンタース乗法（三重指数平滑法）
* ホルトウィンタース加法（三重指数平滑法）
* ホルトウィンタース補正（二重指数平滑法）

各アルゴリズムは、誤差の二乗和（SSE）が最小になるアルゴリズムを決定するために適用されます。次に、平均絶対誤差率（MAPE）および現在の標準誤差が計算され、モデルが統計的に妥当であることが確認されます。

これらのアルゴリズムは、将来の期間における指標の予測を表示するように拡張できます。

トレーニング期間はレポート期間の開始時点によって異なるので、同じ日付に対してレポートされたデータでも、それらが含まれる期間が異なれば、差が生じる可能性があります。

例えば、1 月 1 日から 14 日までのレポートを実行し、次に 1 月 7 日から 21 日までのレポートを実行した場合、この 2 種類のレポートの 1 月 7 日から 14 日までの同じ指標について、異なる予測データが表示される場合があります。これは、トレーニング期間の違いによります。

| レポート期間 | トレーニング期間 |
|--- |--- |
| 1 月 1 日から 14 日まで | 11 月 27 日から 12 月 31 日まで |
| 1 月 7 日から 21 日まで | 12 月 4 日から 1 月 6 日まで |
