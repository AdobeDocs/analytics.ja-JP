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


# resolution

 変数は、Web ページを表示する訪問者の画面の解像度を示します。


<!-- 

resolution.xml

 -->

この変数は、ページコードが開始されてから *`doPlugins`* が実行されるまでの間に設定されます。

> [!NOTE]この変数は読み取り専用です。設定しないでください。

これらの値を読み取り、prop または eVar にコピーすることは可能ですが、値の変更はしないでください。この変数は、JavaScript ファイルのバージョン H.11 で導入されました。

| クエリパラメーター | 値 | 例 | 影響を受けるレポート |
|---|---|---|---|
| s | W x H | 1680 x 1050 | トラフィック／技術／画面の解像度 |

