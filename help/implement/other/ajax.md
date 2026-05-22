---
title: AJAX による実装
description: AJAX を使用して Adobe Analytics をサイトに実装する方法を説明します。
feature: Implementation Basics
exl-id: 3286bf97-3a66-4f68-9053-bf84269962fd
role: Developer
autotag-review: '2026-05-22T08:06:40.936Z'
TQID: 'https://experienceleague.adobe.com/M0MNFZRcHpPwxL-ZtTky67DHDr1A0fL-peaGKicXgIM'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e4f5f438-eabb-4c54-9133-b817e3d125f5
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 373
ht-degree: 100%

---

# AJAX による実装

AJAX は、JavaScript と HTML を使用して、新しいページを読み込まずにコンテンツをクリアし、生成する方法です。

Adobe Analytics は、通常、ページの再読み込みに依存して、Analytics トラッキングオブジェクトをリセットします。 別の URL に移動するたびに、すべての Analytics 変数がリセットされ、再定義できます。 サイトで AJAX を使用する場合は、ページの更新がないことを考慮して実装を調整し、ヒット間でデータが不適切に保持されないようにします。

変数値をクリアする対策を講じた後は、AJAX を使用するサイトに Adobe Analytics を実装する方法は、他の実装方法とほとんど同じです。

## インタラクションとヒットタイプの決定

通常、AJAX を使用するページは再読み込みされないので、ユーザーがサイトでおこなう操作は複数あります。 Adobe Analytics を実装する場合は、ページビュー数とリンクトラッキングコールとを必ず区別してください。 ユーザーがサイトで取ることのできるインタラクションごとに、次の質問を考慮します。

*ユーザーがサイトを操作すると、そのインタラクションは新しいページと見なすのに十分な量のコンテンツをページ上で変更するか。*

* 回答が&#x200B;**はい**&#x200B;の場合、ページビュートラッキングコール（`s.t()`）を使用します。
* 回答が&#x200B;**いいえ**&#x200B;の場合は、リンクトラッキングコール（`s.tl()`）を使用してインタラクションをトラッキングすることを検討します。

>[!NOTE]
>
>すべてのインタラクションまたはクリックを記録する必要はありません。 追跡に最も重要なアクションを慎重に検討し、それに応じてデータをアドビに送信します。

## 各ページの変数のクリア

AJAX を使用するページは再読み込みされないので、変数値が保持されます。 したがって、変数値がヒット間で不適切に保持されないように、特別な調整が必要です。 アドビでは、変数値を簡単にクリアする [`clearVars`](../vars/functions/clearvars.md) 関数を提供しています。 各ヒットをアドビに送信した後、および次のヒットに対して変数値を設定する前に、この関数を必ず使用してください。

>[!TIP]
>
>H コードでは `clearVars()` 関数は使用できません。 AppMeasurement にアップグレードしていない場合は、各 Analytics 変数値を空の文字列に設定します。

## 例

次の例では、単純な JavaScript を使用して、既存の変数値を消去し、新しい値を設定してから、アドビにイメージリクエストを送信します。

```js
s.clearVars();
s.pageName = "Example AJAX page";
s.eVar1="Example value";
void(s.t());
```

以下の例では、JQuery `.ajax` 関数の `done` コールバックでのトラッキングコールを示しています。

```js
$.ajax({
  url: "example.html",
  dataType: "html"
})
  .done(function( response ) {
    $( "#content" ).html( response );
  s.clearVars();
  s.pageName = $( "h1:first" ).text();
  s.t();
  });
```
