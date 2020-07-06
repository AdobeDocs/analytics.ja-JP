---
title: 画面の色
description: デバイスの色深度。
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '220'
ht-degree: 0%

---


# 画面の色

色深度ディメンションは、デバイスがサポートする色数を報告します。 このディメンションは、1600万色をサポートしていないデバイスから発生するトラフィックの量を調べるのに役立ちます。 これまで、このレポートは新しいモバイルWebが登場したときに役に立ちました。 ただし、現在の世代のほとんどのデバイスは1,600万色をサポートしています（0 ～ 255は赤、緑、青）。 <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## このディメンションにデータを入力する

このディメンションは、参照テーブルを参照し、ビット値をより読みやすい形式に変換します。 イメージリクエスト内の [`c` クエリ文字列](/help/implement/validate/query-parameters.md) 、 AppMeasurementは、この変数を使用して `screen.colorDepth` 、イメージリクエストクエリ文字列を設定します。 (Adobe Experience Platformの起動を介したなど)AppMeasurementを使用する場合、このディメンションは初期設定の状態で動作します。 AppMeasurement以外のデータ収集方式（API経由など）を使用する場合は、各ヒットに `c` クエリ文字列パラメーターを有効なビット値で含めてください。

## 分析コード値

寸法値には、デバイスでサポートされる色の数が含まれます。 例えば、、、 `"16 million (24-bit)"`、な `"16 million (32-bit)"`どの値があり `"65,536 (16-bit)"`ます。 AppMeasurementが色深度を判断できない場合は、と表示され `"None"`ます。

>[!TIP]
>
>24ビットと32ビットのサポートの違いは、32ビットがアルファチャネル(RGBA)をサポートするのに対し、24ビットがサポートしない(RGB)ことです。 この概念について詳しくは、Wikipediaの [色深度](https://en.wikipedia.org/wiki/Color_depth) （英語）を参照してください。
