---
title: ドメイン
description: 訪問者がインターネットにアクセスするために使用する組織または ISP。
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
source-git-commit: 35413ac43eed5ab7218794f26e4753acf08f18ee
workflow-type: ht
source-wordcount: '124'
ht-degree: 100%

---

# ドメイン

「ドメイン」ディメンションは、訪問者がインターネットへのアクセスに使用するアクセスポイントを報告します。

## このディメンションへのデータ入力

アドビは、 [Digital Element](https://www.digitalelement.com/) と提携して、アクセスポイントのドメインを判断しています。 アクセスポイントドメインを判断する際には、DNS 逆引き参照を含むいくつかのメソッドを使用します。 構成は不要で、入力する変数もありません。すべての AppMeasurement 実装でデフォルトで動作します。

## ディメンション項目

ディメンション項目の例としては、`comcast.net`、`rr.com`、`sbcglobal.net`、`amazonaws.com` などがあります。これらのドメインはアクセスポイントであり、必ずしも ISP または組織を表すドメインではないことに注意してください。

ディメンション値が `None` の場合は、アクセスポイントの IP アドレスの所有者がドメインを提供しなかったことを意味します。
