---
title: オリジナルの参照ドメイン
description: 訪問者がクリックスルーしてサイトにアクセスする前に閲覧していた最初の参照ドメイン。
feature: Dimensions
exl-id: 6b9ac662-a79a-477b-8612-7980da7cfadd
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '408'
ht-degree: 95%

---

# オリジナルの参照ドメイン

「元の参照ドメイン」 [ ディメンション ](overview.md) は、訪問者がサイトに到達するためにクリックスルーした最初の参照ドメインをレポートします。 設定した後は、その訪問者 ID の有効期間全体で同じ値が含まれます。このディメンションは、サイトへのトラフィックを最初に最も多く促進したサードパーティのサイトを理解するのに役立ちます。

>[!IMPORTANT]
>
>このディメンションを使用するには、レポートスイートの[内部 URL フィルター](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md)を設定する必要があります。内部 URL フィルターを設定しないと、内部ドメインが含まれるか、外部ドメインが表示されない可能性があります。

## このディメンションへのデータ入力

このディメンションは、Analytics インターフェイスとお客様の実装の両方で設定する必要があります。

* 実装内で、このディメンションはイメージリクエストの[`r`クエリ文字列](/help/implement/validate/query-parameters.md)からデータを取得します。AppMeasurement は、ブラウザーの JavaScript `document.referrer` 変数を使用してこのデータを収集します。AppMeasurement ライブラリ（Adobe Experience Platform のタグを介した場合など）を使用する場合、このディメンションは初期設定の状態で動作します。AppMeasurement 以外の（API 経由などの）データ収集方法を使用する場合は、イメージリクエストに `r` クエリ文字列パラメーターを必ず含めてください。
* Analytics のインターフェイス内で、レポートスイートの[内部 URL フィルター](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/internal-url-filter-admin.md) を設定する必要があります。内部 URL フィルターを設定しないと、内部ドメインが含まれるか、外部ドメインが表示されない可能性があります。

アドビは、訪問者が存続する間、オリジナルの参照ドメインを維持します。訪問者が別のドメイン上のリンクを離れたりクリックスルーしたりする場合、新しい値は記録されません。新しい値を表示する場合は、[参照ドメイン](referring-domain.md)を参照してください。

## ディメンション項目

ディメンション項目には、訪問者がサイトにクリックスルーしたドメインが含まれます。ヒットにリファラーデータがない（設定または持続的な）場合は、ディメンション項目 `"None"` でグループ化されます。このディメンション項目は、訪問者がブラウザーのアドレスを手動でアドレスバーに入力したか、ブックマークをクリックしたなど、リファラー値がなかったことを意味します。

## 参照ドメインとオリジナルの参照ドメインの比較

参照ドメインは訪問間で変化する可能性があります。例えば、訪問者が `google.com` 経由でサイトに到達し、その 1 週間後に `twitter.com` 経由でサイトに到達したとします。訪問者は、最終的にはサイトで買い物をします。ラストタッチ属性を持つディメンションとして参照ドメインを使用している場合、`twitter.com` は購入のクレジットを受け取ります。オリジナルの参照ドメインをディメンションとして使用している場合、アトリビューションモデルに関係なく、`google.com` が購入のクレジットを受け取ります。

オリジナルの参照ドメインは、特定の訪問者 ID の有効期間全体を通して変更されません。
