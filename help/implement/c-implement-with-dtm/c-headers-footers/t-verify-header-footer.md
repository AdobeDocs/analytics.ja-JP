---
description: Dynamic Tag Management ライブラリがサイトに適切に読み込まれることを検証します。
keywords: Analyticsの導入;導入方法、Dynamic Tag Management;dtm;code;page code;headerコード;footerコード;embed code;verify code;verify header code;verifyフッターコード;embedタブ;embed
seo-description: Dynamic Tag Management ライブラリがサイトに適切に読み込まれることを検証します。
seo-title: ヘッダーおよびフッターコードの検証
solution: Analytics
title: ヘッダーおよびフッターコードの検証
topic: 開発者と導入
uuid: d395a417-0c61-41a6- a124- d2f400f4626f
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# ヘッダーおよびフッターコードの検証

Dynamic Tag Management ライブラリがサイトに適切に読み込まれることを検証します。

1. ブラウザー（Firefox）でサイトを開きます。
1. Open the [!UICONTROL Developer Console] by right-clicking and choosing **[!UICONTROL Inspect Element]** &gt; **[!UICONTROL Console]**.
1. Press **[!UICONTROL Enter]**.

   If the code was properly installed, you will see *`true`* display in the console.

   コードが適切にインストールされなかった場合、参照エラーが表示されます。

   `_satellite is not defined`

   このエラーが表示される場合は、次のことを確認します：

* [!DNL HEAD] セクション内のサイトのすべてのページに完全なヘッダーコードが含まれており、 [!DNL <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">] タグの近くに配置します。
* ヘッダーコードに見えない全角スペースなど、余計な文字を含めていない（書式付きドキュメントからコピーアンドペーストした結果である可能性がある）。

