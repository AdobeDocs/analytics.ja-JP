---
title: Adobe Experience Platform Mobile SDK を使用した Adobe Analytics の実装
description: Adobe Experience Platform データ収集の Mobile SDK 拡張機能を使用して、Adobe Analytics にデータを送信します。
exl-id: 516e9a1e-caa7-4f8a-ab8c-6404e9242ccb
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '206'
ht-degree: 89%

---

# Adobe Experience Platform Mobile SDK を使用した Adobe Analytics の実装

Adobe Experience Platform Mobile SDK は、モバイルアプリでの Adobe Experience Cloud のソリューションとサービスを強化するのに役立ちます。Android、iOS、および様々なクロスプラットフォーム開発フレームワークで使用できます。設定は、Adobe Experience Platformのデータ収集で処理されます。

Mobile SDK を使用して Adobe Experience Edge にデータを送信するには：

1. [Adobe Experience Platform データ収集](https://experience.adobe.com/data-collection)にログインします。
2. リストから目的のプロパティを選択するか、[モバイルプロパティを設定](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property)します。
3. 「拡張機能」タブに移動し、[Edge ネットワークの ID](https://aep-sdks.gitbook.io/docs/foundation-extensions/identity-for-edge-network) 拡張子ヲインストールします。
4. [Adobe Experience Platform Edge Network](https://aep-sdks.gitbook.io/docs/foundation-extensions/experience-platform-extension) をインストールします。
5. [データストリームの設定](https://aep-sdks.gitbook.io/docs/getting-started/configure-datastreams)を追加し、目的のレポートスイートを指すサービスとして Adobe Analytics を追加します。
6. お使いのモバイルアプリに [SDK をインストール](https://aep-sdks.gitbook.io/docs/getting-started/get-the-sdk)します。

>[!IMPORTANT]
>
>Adobe Analytics拡張機能は、Adobe Experience Platformデータ収集でも使用できます。 この拡張機能をインストールする場合、XDM や Edge ネットワークを利用することはできません。
