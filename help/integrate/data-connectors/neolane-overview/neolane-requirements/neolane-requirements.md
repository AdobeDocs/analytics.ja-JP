---
description: 'Data Connectors統合を開始する前に、以下の要件を満たしている必要があります '
seo-description: 'Data Connectors統合を開始する前に、以下の要件を満たしている必要があります '
seo-title: アクティブ化する前に
title: アクティブ化する前に
uuid: 42eaed67- bcf-4ce3-92c4-932ea1a5b78d
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Before You Activate{#before-you-activate}

Data Connectors統合を開始する前に、以下の要件を満たしています。

## Adobe Analytics Requirements {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **レポートスイート固有:** この統合はレポートスイート固有であることをお勧めします。統合をアクティブ化する前に、目的のレポートスイートを選択していることを確認してください。
* **使用可能なAdobe Analytics変数および設定済みの変数:** この統合にはカスタムイベントとカスタムeVarが必要で、必要に応じて追加のイベントおよび追加のeVarが必要です。See [Adobe Analytics Integration Variables](../../neolane-overview/neolane-requirements/neolane-variables.md#concept-8ebd2bde4a1c4b0aad2987e050ffbbfc).

* **認可された代表者:** この統合の有効化によって、お客様のサービス契約に従って、Adobe， Inc.またはアドビの信頼できるパートナーとのサービス契約に従って料金が課金されることがあります。この統合をアクティブ化することで、貴社の認定担当者であることを表明することになります。そのため、上述のサービス契約で規定されている場合、会社は料金を支払うことに同意します。
* **Data Warehouse™:** この統合には、リマーケティングセグメントを生成するためにData Warehouseを有効にする必要があります。Data Warehouseを有効にしていない場合は、アドビにお問い合わせください。
* ** [!DNL ~Partner~]:** The integration requires that we capture and store a " [!DNL ~Partner~]" within a Adobe Analytics variable (eVar). This ID is an encoded or numeric representation of an email address from the [!DNL ~Partner~] system. This " [!DNL ~Partner~]" is associated with downstream visitor behavior on the site (cart abandons, purchases, etc.) that is pulled into the [!DNL ~Partner~] system and can be leveraged for remarketing purposes. セットアッププロセスの一部として、ウィザードの指示に従って、この目的のeVarを特定する必要があります。
* **外部トラッキング:** 現在、送信する電子メールキャンペーンごとに外部トラッキングを有効にすることをお勧めしていない場合は、統合が正常に完了するようにする必要があります。See the [!DNL ~Partner~] section below for details.
* **プライバシーコンプライアンス:** 受信者または訪問者IDトラッキングを有効にすることで、この機能はサイト訪問者の個人特定情報を追跡することを理解することができます。これには、サイト訪問者に対する通知の提供や同意など、貴社による適切な手順の導入を必要とするプライバシーに関するプライバシーがあります。

## Section Title {#section-370f12579a224d509545cba1c28adb22}

