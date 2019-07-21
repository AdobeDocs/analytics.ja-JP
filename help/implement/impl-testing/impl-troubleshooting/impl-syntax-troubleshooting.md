---
description: 正しいコードと、不正なコードエラーとの違いを表に示します。
keywords: Analytics の導入
seo-description: 正しいコードと、不正なコードエラーとの違いを表に示します。
seo-title: 一般的な構文エラー
solution: Analytics
subtopic: トラブルシューティング
title: 一般的な構文エラー
topic: 開発者と導入
uuid: 9845dcb9-9f10-4f65- a43d-2af41edaa122
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# 一般的な構文エラー

正しいコードと、不正なコードエラーとの違いを表に示します。

| 誤った構文 | 正しい構文 |
|---|---|
| prop1 | s.prop1（「s.」を使用） |
| s.evar1 | s.eVar1（大文字小文字を正しく使用） |
| s.pagetype='errorpage'; | s.pageType='errorPage';（大文字小文字を正しく使用） |
| s.tl(this,o,pageA) | s.tl(this,'o','pageA');（一重引用符を正しく使用） |
| s.events='event1'; s.events='event2'; | s.events='event1,event2';（正しい形式を使用） |
| s.pageName="John"（スマート引用符の使用がオン） | s.pageName="John"（スマート引用符の使用がオフ） |
| s.products="shoes,UX4879,1,19.99" | s.products="shoes;UX4879;1;19.99"（コンマではなくセミコロンを使用） |
| s.products=";MacBook Air;1;$1999.99" | s.products=";MacBook Air;1;1999.99"（ドル記号を使用しない） |
| s.products=";Nikon SB-600 Speedlight Flash for Nikon Digital SLR Cameras;1;229.9489183" | s.products=";Nikon SB-600 Speedlight Flash for Nikon Digital SLR Cameras;1;229.95"（長い表記の価格を丸めるか切り捨てる） |
| var s_account="rsid1, rsid2" | var s_account="rsid1,rsid2"（マルチスイートタギングをおこなう場合はレポートスイート ID 間にスペースを挿入しない） |
| s.events="event1, event2" | s.events="event1,event2"（マルチスイートタギングをおこなう場合はイベント ID 間にスペースを挿入しない） |
| s.products="product name" | s.products=";product name"（製品カテゴリを列挙しない場合はセミコロンを使用する） |

## 追加情報 {#section_E2B6A9C966AD40A09578DD0F784DCAB9}

スクリプトで NOSCRIPT を使用する場合でも、HTML コメント終了は Adobe コードの最後に記述しておいてください。
