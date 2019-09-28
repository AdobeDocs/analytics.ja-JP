---
description: 'null'
keywords: Analytics の実装
seo-description: 'null'
seo-title: アドビオプトアウトの実装
solution: Analytics
title: アドビオプトアウトの実装
topic: 開発者と実装
uuid: fc3a411c-8476-409d-99de-05b34ace5019
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# アドビオプトアウトの実装

Web サイトの訪問者によっては、自分の閲覧情報が Adobe Experience Cloud の製品やサービスによって収集され分析されて、関連コンテンツや関連広告の表示に使用されることを望まない場合があります。アドビでは、Web サイトの訪問者が以下のアドビ製品によって自分の情報が収集されることをオプトアウトできるようにする機能を用意しています。

* Adobe Analytics
* Adobe Target
* Adobe Audience Targeted Creative
* Adobe AudienceManager
* Adobe AdLens
* Adobe Experience Manager

## プライバシーポリシーの推奨事項 {#section_BBDEE21C259842F7881642E31FB3D9B7}

アドビの製品またはサービスによって閲覧情報が収集されることをオプトアウトする機能に関する情報を、Web サイトの訪問者が簡単に見つけ、簡単に理解できるように提示することをお勧めします。

アドビの製品とサービスを顧客に提供するうえで、アドビが収集した情報が一般的にどのように使用されるかという詳細な情報は、[アドビプライバシーセンター](https://www.adobe.com/privacy.html)で参照することができます。ただし、Web サイトにアドビのサービスを導入する方法はサイト運営者にゆだねられているので、Web サイトの訪問者にアドビの製品やサービスの利用方法を訪問者に説明するのは、サイト運営者の責任となります。アドビとのサービス契約に準拠するとともに、適用されるすべての法律に準拠するように、独自のプライバシーポリシーを責任を持って作成してください。

## Opt-outs for Adobe Analytics (including Reports &amp; Analytics, Data Warehouse, Ad Hoc Analysis) {#section_8089B80CDA4043C9BC2DED49E484E8D7}

Adobe offers three types of opt-outs for Adobe Analytics (including [!UICONTROL Reports &amp; Analytics], [!UICONTROL Data Warehouse], [!UICONTROL Ad Hoc Analysis]):

* 独自のファーストパーティcookieを使用してAdobe Analytics製品を実装する場合は、Webサイト訪問者に対して独自にカス [タマイズしたオプトアウトリンクを](../../../implement/js-implementation/data-collection/opt-out-link.md#concept_C2C4F19811A445EF9E9BEAC709B568A9) 、作成する必要があります。
* 顧客は、ブラウザーの cookie 設定を使用してオプトアウトを有効にすることができます。[ブラウザー cookie のプライバシー設定の有効化](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/browser_cookie_settings.html)を参照してください。

どのオプトアウトメカニズムを選択した場合も、プライバシーポリシー（または法律で定められた場所）や、最新のベストプラクティスで推奨されている方法で、そのオプトアウトメカニズムが使用できることを明確に示すことをお勧めします。
