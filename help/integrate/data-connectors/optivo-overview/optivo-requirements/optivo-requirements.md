---
description: 'Data Connectors統合を開始する前に、以下の要件を満たしている必要があります '
seo-description: 'Data Connectors統合を開始する前に、以下の要件を満たしている必要があります '
seo-title: アクティブ化する前に
title: アクティブ化する前に
uuid: 45275635- a80d-46c2- b9ad-985df5737bf2
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
* **使用可能なAdobe Analytics変数および設定済みの変数:** この統合にはカスタムイベントとカスタムeVarが必要です。See [Adobe Analytics Integration Variables](../../optivo-overview/optivo-requirements/optivo-variables.md#concept-8ebd2bde4a1c4b0aad2987e050ffbbfc).

* **認可された代表者:** この統合の有効化によって、お客様のサービス契約に従って、Adobe， Inc.またはアドビの信頼できるパートナーとのサービス契約に従って料金が課金されることがあります。この統合をアクティブ化することで、貴社の認定担当者であることを表明することになります。そのため、上述のサービス契約で規定されている場合、会社は料金を支払うことに同意します。
* **メッセージID:** 統合では、Adobe Analytics変数（eVar）内で「メッセージID"を取得して保存する必要があります。これらのIDは、送信した電子メールを識別するために必要です。セットアッププロセスの一部として、ウィザードの指示に従って、この目的のeVarを特定する必要があります。
* ** [!DNL ~Partner~]:** The integration requires that we capture and store a " [!DNL ~Partner~]" within a Adobe Analytics variable (eVar). This ID is an encoded or numeric representation of an email address from the [!DNL ~Partner~] system. This " [!DNL ~Partner~]" is associated with downstream visitor behavior on the site (cart abandons, purchases, etc.) that is pulled into the [!DNL ~Partner~] system and can be leveraged for remarketing purposes. セットアッププロセスの一部として、ウィザードの指示に従って、この目的のeVarを特定する必要があります。
* **投稿のクリック時間:** セットアッププロセスの一部として、この統合には、ポストクリックアクションの時間に対応するeVarへの割り当てが必要です。This is needed to transmit information about a recipient action to [!DNL ~Partner~] after the recipient clicked a link in a mailing.

* **クリックして製品を投稿:** セットアッププロセスの一部として、この統合には、ポストクリックアクションに関連付けられている提供製品に対応するeVarへの割り当てが必要です。This is needed to transmit information about a recipient action to [!DNL ~Partner~] after the recipient clicked a link in a mailing.

* **アクションのタイプのクリックのタイプ:** この統合では、セットアッププロセスの一部として、ポストクリックアクションのタイプに対応するeVarへの割り当てが必要です。This is needed to transmit information about a recipient action to [!DNL ~Partner~] after the recipient clicked a link in a mailing.

* **プライバシーコンプライアンス:** 受信者または訪問者IDトラッキングを有効にすることで、この機能はサイト訪問者の個人特定情報を追跡することを理解することができます。これには、サイト訪問者に対する通知の提供や同意など、貴社による適切な手順の導入を必要とするプライバシーに関するプライバシーがあります。

## Section Title {#section-370f12579a224d509545cba1c28adb22}

