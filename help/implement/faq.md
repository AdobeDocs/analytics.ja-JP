---
title: 導入FAQ
description: 実装に関するよくある質問と、詳細情報へのリンクです。
translation-type: tm+mt
source-git-commit: b569f87dde3b9a8b323e0664d6c4d1578d410bb7
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 67%

---


# Analytics の実装に関する FAQ

実装に関するよくある質問と、詳細情報へのリンクです。

## Experience Cloud 訪問者 ID と Analytics 訪問者 ID の違いは何ですか。

ID サービスは、Experience Cloud の他のソリューション間で共有できる一意の永続的な識別子を割り当てます。Analytics 訪問者 ID は、Analytics でのみ使用されます。実装に Experience Cloud 訪問者 ID サービスを使用することをお勧めします。

## ハートビートビデオトラッキングを実装する方法を教えてください。

[Adobe Analytics でのオーディオおよびビデオの測定](https://docs.adobe.com/content/help/ja-JP/media-analytics/using/media-overview.html)を参照してください。

## アドビのサービスを中断すると、パフォーマンスに影響を与える可能性はありますか。

いいえ。JavaScript ファイルは、アドビのサーバーでホストされていないでため、アドビの停止状態が AppMeasurement ライブラリに影響することはありません。Adobe Experience Platform Launch を使用する場合、JavaScript ファイルは Akamai または組織が決定したサーバーでホストされます。

##  ブラウザーから Adobe サーバーへのデータの送信によってパフォーマンスが低下することはありますか。

AppMeasurement は、HTML ページ内にイメージオブジェクトを作成し、ブラウザーは、Adobe データ収集サーバーからイメージオブジェクトをリクエストします。データ収集サーバーが低速になったり応答しなくなった場合、そのリクエストを処理するスレッドは、イメージが返されるかタイムアウトが発生するまで、遅延します。ブラウザーはイメージを複数のスレッドで処理するので、アドビの停止状態はページ読み込み時間にわずかな影響しか与えず、1 つのスレッドが停止していても、他のスレッドは機能し続けます。

## Analytics実装を無効にする、または削除する方法を教えてください。

組織では、契約の有効期限切れやサーバーコールの数の減少が原因で実装を削除したい場合があります。

* **Launchを使用した実装**:「 [!UICONTROL 拡張機能] 」タブでAdobe Analytics拡張機能を無効にするかアンインストールして、公開します。
* **従来のAppMeasurementの導入**:ファイルの内容全体を次のコード行に置き換えます。 `s_code.js`

```js
var s = new Object();
```

>[!WARNING]
>
>禁止：
>
>* Adobeのサーバーに不要な読み込みが発生するので、レポートスイートを無効な値に変更します。
>* 各ページのファイルへの参照をすべて削除する場合を除き、 `s_code.js` ファイルを完全に削除します。
>* Adobeから遠ざかるように `trackingServer` 変数を変更します。 AppMeasurementは引き続きイメージリクエストを送信し、404エラーを返します。

