---
description: サイトへの JavaScript およびページコンテンツの読み込みを判断するヘッダーとフッターを、Dynamic Tag Management を使用して追加します。使用するホスティングオプションにかかわらず、サイトのすべてのページにヘッダーとフッターの両方のコードをインストールする必要があります。
keywords: Analyticsの導入;導入方法、Dynamic Tag Management;dtm;code;page code;headerコード;footerコード;embed code;embedタブ;embed
seo-description: サイトへの JavaScript およびページコンテンツの読み込みを判断するヘッダーとフッターを、Dynamic Tag Management を使用して追加します。使用するホスティングオプションにかかわらず、サイトのすべてのページにヘッダーとフッターの両方のコードをインストールする必要があります。
seo-title: ヘッダーおよびフッターコードの追加
solution: Analytics
title: ヘッダーおよびフッターコードの追加
topic: 開発者と導入
uuid: 23d89ae0-340a-4b12-91d1-953b4613c98e
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# ヘッダーおよびフッターコードの追加

サイトへの JavaScript およびページコンテンツの読み込みを判断するヘッダーとフッターを、Dynamic Tag Management を使用して追加します。使用するホスティングオプションにかかわらず、サイトのすべてのページにヘッダーとフッターの両方のコードをインストールする必要があります。

Dynamic Tag Management にはヘッダーとフッターの両方のコードのスニペットが含まれるので、ページの最初または最後にルールを実行できます。この機能により、ページのトラッキングの制御を維持したまま、テスティングツールおよびその他のテクノロジーを導入できます。

Dynamic Tag Management には、ステージングおよび実稼動用の埋め込みコードを作成する機能があります。そのコードは、変更内容を実稼動環境へと反映する前にステージング環境でテストするために使用できます。

>[!IMPORTANT]
>
>導入を成功させるためには、Adobeヘルプに記載されている手順に従うことが重要です。Specifically, you must place the header code in the `<head>` section of your document templates. Also, you must place the footer code just before the closing `</body>` tag. どちらかの埋め込みコードをマークアップの別の場所に配置したり、非同期的な方法で埋め込みコードを追加したり、何らかの方法で埋め込みコードをラッピングしたりする使用方法は、Dynamic Tag Management の導入方法として&#x200B;*サポートされていません*。提供された埋め込みコードは、必ず無変更で実装してください。
>
>サポートされていない導入方法を使用すると、予期しない結果が生じ、カスタマーケアやエンジニアリング担当者が導入の支援をおこなう際に障害となります。

1. Dynamic Tag Management インターフェイスで、「[!UICONTROL 埋め込み]」タブを開き、ホスティングオプション（Akamai など）を選択し、スイッチを「オン」に切り替えます。

   手順1.Dynamic Tag Management の「埋め込み」タブで提供される実稼動用のヘッダーコードをコピーし、サイトの HTML の [!DNL HEAD] セクション内に配置します。

   ![](assets/dtm-embed.png)

   Place the code as close to the [!DNL <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">] タグの近くに配置します。このコードスニペットは、実稼動サイトのすべてのページに配置する必要があります。

   >[!NOTE]
   >
   >Production embed code reflects only the published items in that [property](../../../implement/c-implement-with-dtm/t-create-web-property.md#task_960467FBB7A54499AC228CB3AA3C4123). ただし、ステージングの埋め込みコードは、発行済みまたは未発行の状態にかかわらず、関連するプロパティのすべてのアイテムを反映します。実稼動環境の未発行アイテムをテストするには、[Akamai ホスティング用の未発行のルールのテスト](../../../implement/c-implement-with-dtm/c-rules/t-test-rules-akamai.md#task_B397167F9E9B4487957AD6CE2AD47259)の手順に従って、コンソールでステージングをローカルで有効にします。

1. 実稼動サイト用のフッターコードをコピーして、サイトの HTML の [!DNL BODY] セクションに配置します。

   Place the code as close to the [!DNL </body>] タグの近くに配置します。
1. ステージングのヘッダーおよびフッターコードをコピーして、ステージングサイトで上記の手順を繰り返します。

   >[!NOTE]
   >
   >The difference between production and staging code snippets is the addition of [!DNL -staging] to the filename in the staging version. フッターコードは、ステージングと実稼動で同じです。

