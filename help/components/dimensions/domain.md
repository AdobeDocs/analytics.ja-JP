---
title: ドメイン
description: 訪問者がインターネットにアクセスするために使用する組織または ISP。
translation-type: tm+mt
source-git-commit: c2d371cee2821360ab87240b1a81695798af4f9f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 41%

---


# ドメイン

&#39;Domain&#39;ディメンションは、訪問者がインターネットにアクセスする際に使用するアクセスポイントをレポートします。

## このディメンションへのデータ入力

Adobeは、 [Digital Element](https://info.digitalelement.com/jp/) （デジタル要素）とパートナー関係を持ち、アクセスポイントドメインを決定します。 DNS逆引き参照を含むいくつかのメソッドは、アクセスポイントドメインを決定するために使用されます。 構成は不要で、入力する変数もありません。すべての AppMeasurement 実装でデフォルトで動作します。

## ディメンション項目

ディメンション項目の例としては、`comcast.net`、`rr.com`、`sbcglobal.net`、`amazonaws.com` などがあります。これらのドメインはアクセスポイントであり、ISPや組織を表すドメインとは限りません。

のDimension値は、アクセスポイントIPアドレスの所有者がドメインを提供しなかったことを `None` 意味します。
