---
description: pre 列にはデータ収集に送信されたデータがそのまま含まれます。post 列には処理後の値が含まれます。
keywords: データフィード;job;pre列;post列;大文字と小文字の区別
seo-description: pre 列にはデータ収集に送信されたデータがそのまま含まれます。post 列には処理後の値が含まれます。
seo-title: pre列とpost列
solution: Analytics
title: pre列とpost列
topic: Reports and Analytics
uuid: a415327b-6151-4d08- b8b9-5aa2348eb0c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# pre列とpost列

pre 列にはデータ収集に送信されたデータがそのまま含まれます。post 列には処理後の値が含まれます。

例えば、変数の持続性、処理ルール、VISTA ルール、通貨換算によって、post 列の変数に記録される最終値は変わる可能性があります。（属性の判定にカスタム数式を適用するなど）カスタムビジネスロジックを適用する場合を除き、ほとんどの計算には post 列を使用します。

pre バージョンと post バージョンの区別のない列（`visit_num` など）は、post 列と見なすことができます。Columns prefixed with " `pre_`" typically contain data that was populated by Adobe and not sent by your implementation. For example, `pre_browser` is populated by Adobe, but `evar1` is populated by your implementation. Both of these columns have a " `post_`" column ( `post_browser`, `post_evar1`), which contains the value used by reporting.

## 値の大文字と小文字の区別 {#section_F979E099BFAB4AFEBEA2D7E228963CE8}

大部分の Analytics 変数は、レポート生成の際には大文字と小文字が区別されません。つまり、大文字と小文字の組み合わせが異なるバージョンでも同じ値と見なされます（"snow"、"Snow"、"SNOW"、"sNow" はすべて同じ値と見なされます）。ただし、表示の際には大文字と小文字の区別が維持されます（レポートに表示する文字では大文字と小文字を混在させたいと望む顧客が多いためです）。

データフィードを処理する際に、比較のために値をすべて小文字にする一方で、表示用に大文字と小文字の区別を維持したいことがあります。

pre 列と post 列に、同じ文字の並びで大文字と小文字の組み合わせだけが異なる値が含まれている場合は（pre 列が "snow"、post 列が "Snow" など）、サイト上でその値を大文字バージョンと小文字バージョンの両方で渡していることを示します。post 列内のバージョンは、以前に渡されて仮想 cookie に保存されている値か、同時期にそのレポートスイート用に処理された値です。以下に例を示します。

ヒット 1：s.list1="Tabby,Persian,Siamese”;

ヒット 2：s.list1=“tabby,persian,siamese”;

データフィード内でヒット 2 がレポートされる場合、pre 列には渡されたそのままの大文字小文字の値（tabby,persian,siamese）が格納されますが、その訪問の間はヒット 1 の値が持続する可能性があり、この値が post 列でレポートされます（Tabby,Persian,Siamese になります）。大文字と小文字を区別しない比較が実行される場合、ヒット 1 とヒット 2 にはまったく同じ値が格納されるためです。
