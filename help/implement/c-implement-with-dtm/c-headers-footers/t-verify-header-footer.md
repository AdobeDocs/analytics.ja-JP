---
description: Dynamic Tag Management ライブラリがサイトに適切に読み込まれることを検証します。
keywords: Analytics の実装, 実装方法, dynamic tag management, dtm, コード, ページコード, ヘッダーコード, フッターコード, 埋め込みコード, コードの検証, ヘッダーコードの検証, フッターコードの検証, 「埋め込み」タブ, 埋め込み
seo-description: Dynamic Tag Management ライブラリがサイトに適切に読み込まれることを検証します。
seo-title: ヘッダーおよびフッターコードの検証
solution: Analytics
title: ヘッダーおよびフッターコードの検証
topic: 開発者と実装
uuid: d395a417-0c61-41a6-a124-d2f400f4626f
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# ヘッダーおよびフッターコードの検証

Dynamic Tag Management ライブラリがサイトに適切に読み込まれることを検証します。

1. ブラウザー（Firefox）でサイトを開きます。
1. 右クリックして&#x200B;**[!UICONTROL 要素を調査]**／**[!UICONTROL コンソール]**&#x200B;を選択することで、[!UICONTROL 開発者コンソール]を開きます。
1. **[!UICONTROL Enter]** を押します。

   コードが正しくインストールされている場合は、コンソールに *`true`* が表示されます。

   コードが適切にインストールされなかった場合、参照エラーが表示されます。

   `_satellite is not defined`

   このエラーが表示される場合は、次のことを確認します：

* サイトのすべてのページで、[!DNL HEAD] セクションの、[!DNL  タグのできるだけ近くに、完全なヘッダーコードが含まれている。<head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8">] タグの近くに配置します。
* ヘッダーコードに見えない全角スペースなど、余計な文字を含めていない（書式付きドキュメントからコピーアンドペーストした結果である可能性がある）。

