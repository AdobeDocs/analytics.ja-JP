---
description: デバイス間の訪問者の識別では、デバイス間の訪問者を関連付けます。デバイス間の訪問者の識別では、訪問者 ID 変数の s.visitorID を使用して、デバイス間のユーザーを関連付けます。
keywords: Analytics Implementation
subtopic: Visitors
title: デバイス間のユーザーの接続
topic: Developer and implementation
uuid: 6243957b-5cc1-49ef-aa94-5b5ec4eac313
translation-type: tm+mt
source-git-commit: 0439440e10dddf8a5d64e4ea8f9868b521e5ca20

---


# デバイス間のユーザーの接続

> [!IMPORTANT]デバイスをまたいで訪問者を識別するこの方法は、非推奨になりました。コンポー [ネントユーザーガイドの](/help/components/cda/cda-home.md) 「デバイス間の分析」を参照してください。

デバイス間の訪問者の識別では、デバイス間の訪問者を関連付けます。Cross-device visitor identification uses the `visitorID` variable to associate a user across devices. この変 `visitorID` 数は、個別訪問者を識別する際に最も高い優先順位を持ちます。

カスタム訪問者IDを使用してヒットを送信すると、アドビは、一致する訪問者IDを持つ訪問者プロファイルを確認します。 訪問者プロファイルが存在する場合は、その時点から既にシステムに存在する訪問者プロファイルが使用され、以前の訪問者プロファイルは使用されなくなります。

Setting the `visitorID` variable is typically set after authentication, or after a visitor performs some other action that allows you to uniquely identify them independently of the device that is used. 有効な識別子には、ユーザ名のハッシュ、電子メールアドレス、または個人を特定できる情報を含まない内部IDが含まれます。

顧客が各デバイスからログインすると、それらはすべて同じユーザープロファイルに関連付けられます。 訪問者が後でデバイスにサインアウトした場合、アドビは各デバイスのブラウザーcookieが同じ訪問者プロファイルに属していると認識するので、訪問者は引き続き同じ訪問者プロファイルに属します。 ブラウザーのCookieが削除さ `visitorID` れた場合に備えて、可能な限りこの変数を使用することをお勧めします。

## 制限事項

独自のカスタム訪問者IDを使用すると、訪問者の識別方法をより詳細に制御できますが、制限があります。

* **訪問者の重複除外は遡及的ではありません**。訪問者が初めてサイトにアクセスし、認証を行うと、2人の個別訪問者がカウントされます。 汎用のAnalytics IDに対して1人の実訪問者が自動的にカウントされ、ログイン時に別のカスタム訪問者IDに対してカウントされます。 この個別訪問者数の重複は、訪問者が新しいデバイスを使用したり、cookieをクリアしたりするたびに発生します。
* **Experience Cloud IDサービスとの非互換性**:デバイス間の訪問者の識別が導入されて以来、アドビでは、デバイス間で訪問者を追跡するためのより強力で信頼性の高い方法をリリースしました。 これらの新しい識別方法は、カスタム訪問者IDの上書きと互換性がありません。 IDサービス、Cross-device Analytics(CDA)またはDevice Co-opを使用する予定の場合は、この変数の使用を強くお勧めしま `visitorID` す。
