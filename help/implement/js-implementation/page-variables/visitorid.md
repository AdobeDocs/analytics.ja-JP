---
description: ページ変数は、pageName、リスト Prop、リスト変数など、レポートに直接入力されます。
keywords: Analytics Implementation
subtopic: Variables
title: ページ変数
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# visitorID

ランダムで発行される ID の代わりに、 変数で任意のIDを指定することもできます


<!-- 

visitorID.xml

 -->

*`visitorID`* は最大 100 文字の英数字で指定でき、ハイフンを含めることはできません。

カスタム ID を明示的に設定する場合は、常に他の ID メソッドの前に使用する必要があります。

使用順序は s.visitorID &gt; s_vi &gt; s_fid &gt; IP/UA です。

| ** 最大サイズ** | ** デバッガーパラメーター** | ** 入力されるレポート** | ** デフォルト値** |
|---|---|---|---|
| 100 バイト | vid | 該当なし | "" |

**構文と可能な値** {#section_5F768C7AE6824557997E92B295C09280}

```js
s.visitorID="visitor_id"
```

> [!NOTE]*`visitorID`* 変数にハイフンを含めないでください。

**例** {#section_F7F07FEFAC3644A5A084D166ACE1315E}

```js
s.visitorID="abc123"
```

**設定** {#section_582B376FE55C4BCA8F978E0F62B5DB54}

なし
