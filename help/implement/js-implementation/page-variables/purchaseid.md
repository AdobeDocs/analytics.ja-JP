---
description: ページ変数は、pageName、リスト Prop、リスト変数など、レポートに直接入力されます。
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: ページ変数
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 45642bdbe18627caa20b1def6443f1e596a41f52

---


# purchaseID

 は、レポートで注文が複数回カウントされるのを防ぐために使用します。

<!-- 

purchaseID.xml

 -->

[!UICONTROL 購入]イベントがサイトで使用される場合は必ず *`purchaseID`* 変数を使用する必要があります。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 20 バイト | purchaseID | コンバージョン／購入／売上高、コンバージョン | "" |

訪問者がサイトで品目を購入したとき、*`purchaseID`* が、[!UICONTROL 購入]イベントが発生した「ご購入ありがとうございました」ページに対して設定されます。*`purchaseID`* が生成されると、「ご購入ありがとうございました」ページ上の製品が&#x200B;*`purchaseID`* ごとに 1 回カウントされます。サイトへの多くの訪問者が、それぞれの目的で「ご購入ありがとうございました」ページ（「確認ページ」）を保存するので、1 回だけカウントされることは非常に重要です。Folio Builder *`purchaseID`* は、ページが表示されるたびに購入がカウントされるのを防ぎます。

*`purchaseID`*&#x200B;を使用することで、購入データが 2 回カウントされるのを防ぐだけでなく、すべてのコンバージョンデータがレポートで二重にカウントされるのを防ぎます。

**構文と可能な値** {#section_E352CE2370D54BA69A368E1F63A9C32D}

```js
s.purchaseID="unique_id"
```

*`purchaseID`* は 20 文字以下で、標準の ASCII 文字を使用する必要があります。

**例** {#section_60A5C1EAF42F4611898CD6A4F4CF5A28}

```js
s.purchaseID="11223344" 
s.purchaseID="a8g784hjq1mnp3"
```

**設定** {#section_1808631C96674380BF9C4A6D9A2C568E}

なし

**注意事項、質問、ヒント** {#section_F5D010F234ED43F19AD1FCD2CD64E060}

*`purchaseID`* 変数を使用すると、レポートで、ページ上のすべてのコンバージョン変数が 1 回だけカウントされます。
