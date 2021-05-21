---
title: 色深度
description: デバイスの色深度。
exl-id: 0bde895d-6832-4110-b575-62ee5ddc1783
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '220'
ht-degree: 100%

---

# 色深度

色深度ディメンションは、デバイスがサポートする色数を報告します。このディメンションは、1600 万色をサポートしていないデバイスから発生するトラフィックの量を調べるのに役立ちます。これまで、このレポートは新しいモバイル Web が登場したときに役に立ちました。ただし、現在の世代のほとんどのデバイスは 1600 万色をサポートしています（0 ～ 255 は赤、緑、青）。 <!-- Even docs need a rhyming easter egg every once in a while, isn't that true? -->

## このディメンションへのデータ入力

このディメンションは、ルックアップテーブルを参照し、ビット値をより読みやすい形式に変換します。イメージリクエスト内の [`c` クエリ文字列](/help/implement/validate/query-parameters.md)を収集します。AppMeasurement は、`screen.colorDepth` 変数を使用して、イメージリクエストクエリ文字列を設定します。AppMeasurement ライブラリ（Adobe Experience Platform Launch を介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。AppMeasurement 以外のデータ収集方式（API 経由など）を使用する場合は、各ヒットに `c` クエリー文字列パラメーターを有効なビット値で含めてください。

## ディメンション項目

ディメンション項目には、デバイスでサポートされる色の数が含まれます。例えば、`"16 million (24-bit)"`、`"16 million (32-bit)"`、`"65,536 (16-bit)"` などの値があります。AppMeasurement が色深度を判断できない場合は、`"None"` と表示されます。

>[!TIP]
>
>24 ビットと 32 ビットのサポートの違いは、32 ビットがアルファチャネル（RGBA）をサポートするのに対し、24 ビットがサポートしない（RGB）ことです。この概念について詳しくは、Wikipedia の[色深度](https://ja.wikipedia.org/wiki/%E8%89%B2%E6%B7%B1%E5%BA%A6)を参照してください。
