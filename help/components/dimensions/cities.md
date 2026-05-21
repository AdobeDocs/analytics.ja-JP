---
title: 市区町村
description: ヒットの元となった市区町村。
feature: Dimensions
exl-id: c04525bb-50d6-4d28-b5dc-335d089e184b
TQID: https://experienceleague.adobe.com/tAr9M0IgZcpRzElFfQSJx43JJjIXEtlo-pgDAKpSwq0
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 375
ht-degree: 74%

---

# 市区町村

「都市」 [&#x200B; ディメンション &#x200B;](overview.md)は、ヒットの発生元の都市を報告します。 このディメンションは、サイトの訪問時に最も人気のある訪問者の出所を判断するのに役立ちます。 このデータを使って、市区町村での広告掲示板やコマーシャルなどの地域広告に焦点を当てることができます。

## このディメンションへのデータ入力

このディメンションは、Adobe 内部のルックアップルールを参照します。 ルックアップ値は、ヒットと共に送信される IP アドレスに基づきます。 Adobeは[Digital Element](https://www.digitalelement.com/)と提携して、IP アドレスと市区町村間のルックアップを管理します。

* AppMeasurementの実装では、このディメンションはそのまま機能します。
* Web SDKの実装の場合、[&#x200B; データストリームの設定](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=ja)時に[!UICONTROL Geo Lookup]を有効にします。

## ディメンション項目

ディメンション項目には、世界中の区市町村が含まれます。 例えば、`"New York (New York, United States)"`、`"Bangalore (Karnataka, India)"`、`"London (London, United Kingdom)"` の値があります。

ディメンション項目には、ダイヤルアップインターネットサービスプロバイダーの `"AOL"` などが含まれる場合があります。 このサービスの購読者には、アカウント番号が確立された国に基づいてアクセスポイントが割り当てられます。 AOL ユーザーは、このアクセスポイントの IP アドレスを使用します。 このディメンションは IP アドレスに基づいているので、訪問者の実際の場所の代わりに、アクセスポイントの位置情報が使用されます。

## レポート場所と実際の場所の違い

このディメンションは IP アドレスに基づいているので、レポートされた場所と実際の場所の違いを示すシナリオもあります。

* **企業プロキシを表す IP アドレス**：これらの訪問者は、ユーザーの会社のネットワークを通るトラフィックとして表示される場合があります。ユーザーがリモートで作業している場合は、別の場所に配置することができます。
* **モバイル IP アドレス**：モバイル IP ターゲティングは、場所とネットワークに応じて様々なレベルで機能します。 一部の通信事業者は、IP トラフィックを一元化されたポイントまたは地域のポイントからバックホールします。
* **Satellite ISP ユーザー**：これらのユーザーは通常、アップリンクの場所から派生しているように見えるので、特定の場所を識別するのは困難です。
* **軍事および政府の知的財産**：これはしばしば、人員が現在滞在しているベースやオフィスというより、世界中を旅行する人員がホーム場所を経由して入って来ていることを表します。
* プライバシー上の理由からIP アドレスを不明瞭にする&#x200B;**プロキシ**: Appleのプライベートリレーなどのサービスは、仲介者またはプロキシを介してデータをランダムに送信することで、真のIP アドレスを非表示にします。 このプロキシは、Adobeに転送する前に別のIP アドレスに置き換わります。
