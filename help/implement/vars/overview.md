---
title: 変数、関数、メソッド、プラグインの概要
description: レポートを改善するためにアドビに送信するデータに含めることができる変数について説明します。
keywords: appmeasurement、変数、vars、設定、ページ、実装
feature: Variables
exl-id: 7ffcd943-f9ac-4daf-bbdf-248d75925b04
role: Admin, Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '387'
ht-degree: 69%

---

# 変数、関数、メソッド、プラグインの概要

Analytics には、Analytics データを収集するための変数が多数用意されています。この節の変数は、いくつかに分かれています。

* **ページ変数**&#x200B;は、通常、レポートで直接使用される値です。一般的なページ変数には、`props`、`eVars`、`events` が含まれます。
* **設定変数**&#x200B;は、正しいデータがアドビに届くことを確認するのに役立つ設定値です。一般的な設定変数には、`trackingServerSecure`、`charSet`、`linkTrackVars` があります。通常、設定変数はディメンション項目を設定しません。
* **関数とメソッド**&#x200B;は、参照時に特定のタスクを実行するコードの一部です。一般的な関数には、`t()`、`tl()`、`clearVars()` があります。

## 変数と実装メソッド

Adobe Analytics は様々な方法で実装できます。各ページには、Web SDK を使用した変数の実装方法、Adobe Analytics拡張機能の使用方法、JavaScript 版AppMeasurementの使用方法に関する節があります。

Adobe Analytics での変数の設定に関するビデオを以下に示します。

>[!VIDEO](https://video.tv.adobe.com/v/28755/?quality=12)

## 演算の順序

Adobe Analytics によって公開された AppMeasurement ライブラリは、アドビにデータを送信する際に、特定の順序に従います。これらのタスクを順不同で実行すると、データが不完全になる可能性があります。

1. サイトでデータレイヤーを使用している場合は、該当するすべての変数が最初に入力されていることを確認します。例えば、 `adobeDataLayer.page.title` をページタイトルに追加します。 詳しくは、[データレイヤー](../prepare/data-layer.md)を参照してください。
2. データレイヤーを使用して Analytics 変数を入力します。<br/>Adobe Experience Platformでタグを使用する場合、このタスクはその間にデータ要素を使用して実行されます。 データ要素には、データレイヤーの値が設定されます。 例：データ要素 `Page Title` データレイヤー変数から値を取得します `adobeDataLayer.page.title`. <br/>その後、データ要素を使用して Analytics 変数を設定できます。 例： `eVar4` データ要素から値を取得します `Page Title`. <br/>詳細については、を参照してください。 [データ要素](https://experienceleague.adobe.com/docs/experience-platform/tags/ui/data-elements.html?lang=ja), [データレイヤーオブジェクトをデータ要素にマッピングする](../launch/layer-to-elements.md)、および [タグデータ要素を Analytics 変数にマッピングする](../launch/elements-to-variable.md)
3. 最後に、トラッキング関数を呼び出します。 ほとんどの AppMeasurement ライブラリでは `t()` メソッドを使用しますが、一部の モバイル SDK では `track()` メソッドを使用します。トラッキング関数が呼び出されると、Analytics オブジェクトで定義されたサポートされているすべての変数が、イメージリクエストの形式でアドビに送信されます。

## 無効な文字

次の文字と文字列は、JavaScript 変数では使用できません。

* タブ（`0x09`）
* キャリッジリターン（`0x0D`）
* 改行（`0x0A`）
* HTML タグ（例：`<b></b>`、`&#153`）

一部の変数には、追加の制限や構文上の要件があります。例えば、[`products`](page-vars/products.md) 変数は製品とカテゴリを区切るためにセミコロンとコンマを予約します。
