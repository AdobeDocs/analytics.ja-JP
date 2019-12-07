---
description: データフィードに関するよくある質問(FAQ)
keywords: Data Feed;job;pre column;post column;case sensitivity
title: データフィードFAQ
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# データフィードFAQ

データフィードに関するよくある質問(FAQ)です。

## プレフィックスのある列とプレフィックスのな `post_` い列の違いは何で `post_` すか。

プレフィックスのない `post_` 列には、データ収集に送信されたデータと完全に同じデータが含まれます。 処理後の値は、プ `post_` レフィックスの付いた列に格納されます。 値を変更できる例としては、変数の持続性、処理ルール、VISTAルール、通貨換算、その他のサーバー側ロジックが挙げられます。 可能な限り、列のバージ `post_` ョンを使用することをお勧めします。

If a column does not contain a `post_` version (for example, `visit_num`), then the column can be considered a post column.

## データフィードで大文字と小文字の区別を扱う方法

Adobe Analyticsでは、ほとんどの変数は、レポートの目的で、大文字と小文字が区別されません。 例えば、「snow」、「Snow」、「SNOW」、「sNow」はすべて同じ値と見なされます。 大文字と小文字の区別は、データフィードで保持されます。

投稿以外の列と投稿の列の間で同じ値の大文字と小文字の違いが見られる場合（例えば、pre列に「snow」、post列に「Snow」）、サイト全体で大文字と小文字の両方の値が使用されます。 post 列内のバージョンは、以前に渡されて仮想 cookie に保存されている値か、同時期にそのレポートスイート用に処理された値です。