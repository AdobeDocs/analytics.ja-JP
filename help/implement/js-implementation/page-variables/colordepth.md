---
description: ページ変数は、pageName、リスト Prop、リスト変数など、レポートに直接入力されます。
keywords: Analytics Implementation
subtopic: Variables
title: ページ変数
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# colorDepth

 変数は、画面の各ピクセルで色を表示するためのビット数を示すために使用します。


<!-- 

colordepth.xml

 -->

例えば、「32」は、画面上の色が 32 ビットであることを示します。この変数は、ページコードが開始されてから *`doPlugins`* が実行されるまでの間に設定されます。

> [!NOTE]この変数は読み取り専用です。設定しないでください。

これらの値を読み取り、`props/eVars` にコピーすることは可能ですが、値の変更はしないでください。この変数は、JavaScript ファイルのバージョン H.11 で導入されました。

| クエリパラメーター | 値 | 例 | 影響を受けるレポート |
|---|---|---|---|
| c | 8、16 および 32 | 32 | トラフィック／技術／画面の色設定 |
