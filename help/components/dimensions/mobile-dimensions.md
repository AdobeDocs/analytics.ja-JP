---
title: モバイル参照ディメンション
description: Dimensionの IP アドレスとユーザーエージェントに基づくデバイス。
feature: Dimensions
exl-id: fa460888-513d-4d14-93b1-33d308e0758a
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 60%

---

# モバイル参照ディメンション

*このページでは、Web サイトにアクセスするモバイルデバイスのプロパティを参照します。 詳しくは、 [モバイルのライフサイクルディメンション](lifecycle-dimensions.md) または [モバイルのライフサイクル指標](../metrics/lifecycle-metrics.md) モバイルアプリ内での追跡用。*

モバイル参照 [寸法](overview.md) は、サイトを訪問したモバイルデバイスのプロパティに関するインサイトを提供します。 これらのプロパティは、ユーザーエージェントとヒットの IP アドレスに基づきます。 これらのサイズを使用して、モバイルデバイスがサポートする機能を理解できます。

## これらのディメンションにデータを入力する

これらのディメンションは、Adobe 内部のルックアップルールを参照します。

* の [!UICONTROL 携帯電話会社] ディメンション、Adobeパートナー [デジタル要素](https://www.digitalelement.com/) NetAcuity を使用して、IP アドレスと携帯電話会社間の検索を維持する。
* その他すべてのモバイルディメンションについて、Adobeパートナーは [DeviceAtlas](https://deviceatlas.com/) ユーザーエージェントと各モバイルディメンション間の検索を維持する。

これらのディメンションの使用可否は、実装タイプによって異なります。

* AppMeasurement実装の場合、これらのディメンションは初期設定の状態で動作します。
* Web SDK 実装の場合、を有効にします。 [!UICONTROL 地域ルックアップ] （携帯電話会社の場合）または [!UICONTROL デバイス参照] （他のすべてのディメンションの場合） [データストリームの設定](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja).

## モバイルディメンションの説明

>[!NOTE]
>
>`"None"` ラベルの付いたディメンション項目は、モバイルデバイス以外のデバイスです。モバイルデバイスのみを含むレポートを作成する場合は、「モバイルデバイス」ディメンションを Workspace キャンバスのセグメント領域にドラッグします。

* **[!UICONTROL モバイルオーディオサポート]**：デバイスで再生できるファイル形式を指定します。例えば、`"MP3"`、`"AAC"`、`"MIDI Monophonic"` などの値があります。このディメンションの値は、相互に排他的ではありません。単一のヒットは、複数のディメンション項目を属性にすることができます。
* **[!UICONTROL 携帯電話会社]**：デバイスの電話またはデータプロバイダー。 例えば、`"Reliance Jio"`、`"Airtel"`、`"Vodafone"`、`"Verizon"` などの値があります。
* **[!UICONTROL モバイルの画面の色]**：モバイルデバイスの色深度（ビット）。
* **[!UICONTROL モバイル cookie のサポート]**：モバイルデバイスが cookie をサポートするかどうかを指定します。ブラウザーが cookie を受け入れた場合、このディメンションは状態になりません。 ディメンション項目の値には、`"Supported"`、`"Not supported"`、`"Unknown"` が含まれます。
* **[!UICONTROL モバイルデバイス]**：訪問者が使用するモバイルデバイス。
* **[!UICONTROL モバイルデバイス番号]**：モバイルデバイスがその番号を送信するかどうかを指定します。このディメンションは、モバイル番号自体を提供しません。 ディメンション項目の値には、`"Supported"`、`"Not supported"`、`"Unknown"` が含まれます。
* **[!UICONTROL モバイルデバイスタイプ]**：モバイルデバイスの種類。例えば、`"Mobile phone"`、`"Tablet"`、`"Media player"`、`"Gaming console"` などの値があります。
* **[!UICONTROL モバイル DRM]**：モバイルデバイスがサポートする DRM のタイプ。 例えば、`"DRM OMA forward"`、`"DRM OMA combined delivery"`、`"DRM OMA separate delivery"` などの値があります。
* **[!UICONTROL モバイルの画像サポート]**：モバイルデバイスがサポートする画像のタイプ。 例えば、`"PNG"`、`"JPEG"`、`"GIF 87"` などの値があります。このディメンションの値は、相互に排他的ではありません。単一のヒットは、複数のディメンション項目を属性にすることができます。
* **[!UICONTROL モバイル情報サービス]**：デバイスでサポートされているニュースサービスの種類。最新のデバイスでは、通常、この情報はレポートされません。
* **[!UICONTROL モバイル Java Vm：デバイスがサポートする]**：デバイスがサポートする Java のバージョン。
* **[!UICONTROL モバイルデコレーションメール]**：デバイスがをサポートするかどうかを決定します。 [デコメ](https://en.wikipedia.org/wiki/Decome)は、かつて日本のデバイスで人気があった機能です。
* **[!UICONTROL モバイルの製造元]**：モバイルデバイスを製造元別に分類します。 例えば、`"Apple"`、`"Samsung"`、`"Huawei"`、`"Motorola"` などの値があります。
* **[!UICONTROL モバイルのブックマーク最大長]**：ブックマークされた URL でモバイルデバイスがサポートする最大バイト数です。最新のデバイスには通常、制限はありません。
* **[!UICONTROL モバイルブラウザー URL の最大長]**：モバイルデバイスが URL でサポートする最大バイト数です。最新のデバイスには通常、制限はありません。
* **[!UICONTROL モバイルの電子メールの最大長]**：モバイルデバイスが電子メールでサポートする最大バイト数です。最新のデバイスには通常、制限はありません。
* **[!UICONTROL モバイルネットプロトコル]**：インターネットにアクセスする際にデバイスがサポートするプロトコルの種類です。例えば、`"EDGE"`、`"GPRS"`、`"UMTS"`、`"LTE"` などの値があります。
* **[!UICONTROL モバイルオペレーティングシステム（非推奨）]**：代わりに、[オペレーティングシステム](operating-systems.md)ディメンションを使用します。
* **[!UICONTROL モバイルプッシュトゥトーク]**：デバイスが PTT（プッシュして通話）をサポートしているかどうかを判定します。これにより、モバイルデバイスは双方向無線と同じように動作します。最新のデバイスでは、通常、この機能はレポートされません。
* **[!UICONTROL モバイルの画面の高さ]**：画面の高さ（ピクセル単位）。iPhone は常にレポートします `"480"` iPhoneデバイスのバージョンを判断できないためです。 iPhoneデバイスのバージョンの確認については、以下の節を参照してください。
* **[!UICONTROL モバイルの画面サイズ]**：モバイルデバイスの最大寸法（ピクセル単位）。報告される画面サイズは、デバイスの向きを示していません。画面の向きに関係なく、各デバイスの固定された画面解像度がレポートに示されます。このサイズは、どの向きがよく使用されるかを判断する調査に基づいています。同じレポート内で、`"768x1024"` や `"1024x768"` というサイズがそれぞれ 1 つまたは複数のデバイスを表す場合があります。
* **[!UICONTROL モバイルの画面の幅]**：画面の幅（ピクセル単位）。
* **[!UICONTROL モバイルビデオサポート]**：モバイルデバイスがサポートするビデオファイル形式とコーデック。MP4 と 3GPP ファイルのコーデックには、複数のディメンション項目が存在します。このディメンションの値は、相互に排他的ではありません。単一のヒットは、複数のディメンション項目を属性にすることができます。

## モデル別またはバージョン別に iPhone を分割

モバイルデバイスでは、デバイスバージョンではなく、ユーザーエージェント文字列のファームウェアバージョンが表示されます。例えば、現在の iPhone が同じファームウェアバージョンの場合、最新世代 iPhone と同じユーザーエージェントを含むとします。JavaScript を使用して iPhone のデバイスバージョンを判断する方法がないので、すべての iPhone は同じグループに属しています。モバイルディメンションは、ユーザーエージェントを参照する参照に厳密に基づいているので、すべての iPhone でモバイルの画面サイズが `320 x 480`.

iPhoneデバイスのバージョンを収集する場合は、この制限を回避する方法が 2 つあります。

* **Mobile SDK の使用**:Mobile SDK には、レポートで使用するデバイスのバージョンを公開するディメンションが含まれています。 この方法は、Web サイトよりもモバイルアプリに最適です。
* **JavaScript で使用できるその他の変数を使用します。** `screen.height` および `screen.width` などの一部の変数は、デバイスのバージョンを推論するために使用できます。例えば、サイト上の次のコードのスニペットを使用できます。

  ```js
  if (navigator.userAgent.indexOf('iPhone') > -1) {
    s.eVarXX = screen.width + "x" + screen.height;
    }
  ```

  このコードブロックは、まずデバイスが iPhone であるかどうかを検出します。画面の解像度が高い場合、コードは JavaScript を使用して eVar に画面の解像度を取り込みます。この方法を使用すると、画面の解像度が一意の場合に、デバイスのバージョンをほぼ検出できます。
