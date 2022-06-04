---
title: Adobe Experience Platform Mobile SDK を使用したAdobe Analyticsの実装
description: Adobe Experience Platformデータ収集の Mobile SDK 拡張機能を使用して、Adobe Analyticsにデータを送信します。
source-git-commit: 6979736e1849d25af2141e0ab76a143605a90620
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 6%

---


# Adobe Experience Platform Mobile SDK を使用したAdobe Analyticsの実装

Adobe Experience Platform Mobile SDK は、モバイルアプリでAdobeのExperience Cloudソリューションおよびサービスを強化するのに役立ちます。 Android、iOS、および様々なクロスプラットフォーム開発フレームワークで使用できます。 設定は、Adobe Experience Platformデータ収集 UI を通じて処理されます。

Mobile SDK を使用して Adobe Experience Edge にデータを送信するには：

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection).
2. リストから目的のプロパティを選択します。または [モバイルプロパティの設定](https://aep-sdks.gitbook.io/docs/getting-started/create-a-mobile-property).
3. 「拡張機能」タブに移動し、 [Edge ネットワークの ID](https://aep-sdks.gitbook.io/docs/foundation-extensions/identity-for-edge-network) 拡張子。
4. のインストール [Adobe Experience Platform Edge Network](https://aep-sdks.gitbook.io/docs/foundation-extensions/experience-platform-extension).
5. [データストリームの設定](https://aep-sdks.gitbook.io/docs/getting-started/configure-datastreams)を追加し、目的のレポートスイートを指すサービスとしてAdobe Analyticsを追加します。
6. [SDK のインストール](https://aep-sdks.gitbook.io/docs/getting-started/get-the-sdk) を使用して、製品内で利用できます。

>[!IMPORTANT]
>
>Adobe Analytics拡張機能は、データ収集 UI でも使用できます。 この拡張機能をインストールする場合、XDM や Edge ネットワークを利用することはできません。
