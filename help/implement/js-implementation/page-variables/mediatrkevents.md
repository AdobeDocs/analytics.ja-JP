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


# media.trackEvents

 変数は、どのイベントがメディアヒットと共に送信されるかを示します。


<!-- 

media_trackEvents.xml

 -->

この変数は、JavaScript と [!UICONTROL ActionSource] でのみ適用できます。

| 最大サイズ | デバッガーパラメーター | 入力されるレポート | デフォルト値 |
|---|---|---|---|
| 該当なし | 該当なし | 該当なし | s.Media.trackEvents="None" |

**構文と可能な値** {#section_66A978EF56914BEAAE73359A268A1B4A}

event1、purchase などのイベント名。

**例** {#section_140A55D80EA24011954F9383CF312237}

```js
s.Media.trackEvents="event1,purchase"
```

**注意事項、質問、ヒント** {#section_030B11C64EE84D46A85CA550DB732D28}

この変数を入力するときは、必ず [!UICONTROL trackVars] に "events" と入力してください。
