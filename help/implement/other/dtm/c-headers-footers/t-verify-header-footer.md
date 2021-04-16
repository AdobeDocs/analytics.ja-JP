---
description: Dynamic Tag Management ライブラリがサイトに適切に読み込まれることを検証します。
keywords: Analytics の実装, 実装方法, dynamic tag management, dtm, コード, ページコード, ヘッダーコード, フッターコード, 埋め込みコード, コードの検証, ヘッダーコードの検証, フッターコードの検証, 「埋め込み」タブ, 埋め込み
title: ヘッダーおよびフッターコードの検証
topic-fix: Developer and implementation
uuid: d395a417-0c61-41a6-a124-d2f400f4626f
exl-id: bed44ba7-8e0e-49e2-bedc-fb1ba66e5b18
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '162'
ht-degree: 100%

---

# ヘッダーおよびフッターコードの検証

Dynamic Tag Management ライブラリがサイトに適切に読み込まれることを検証します。

1. ブラウザー（Firefox）でサイトを開きます。
1. 右クリックして、**[!UICONTROL 要素を調査]**／**[!UICONTROL コンソール]**&#x200B;を選択することで、[!UICONTROL Web コンソール]を開きます。
1. **[!UICONTROL Enter]** を押します。

   コードが正しくインストールされている場合は、コンソールに *`true`* が表示されます。

   コードが適切にインストールされなかった場合、参照エラーが表示されます。

   `_satellite is not defined`

   このエラーが表示される場合は、次のことを確認します：

* サイトのすべてのページで、[!DNL HEAD] セクションの、`<head>` タグのできるだけ近くに、完全なヘッダーコードが含まれている。 タグの近くに配置します。
* ヘッダーコードに見えない全角スペースなど、余計な文字を含めていない（書式付きドキュメントからコピーアンドペーストした結果である可能性がある）。
