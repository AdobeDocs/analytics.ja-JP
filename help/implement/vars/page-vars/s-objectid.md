---
title: s_objectID
description: Activity Map で、サイト上の一意のリンクを識別します。
feature: Variables
exl-id: 7c0cb750-2bfe-41ca-ab27-30dda4b3a7fa
role: Admin, Developer
source-git-commit: 72b38970e573b928e4dc4a8c8efdbfb753be0f4e
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 80%

---

# s_objectID

`s_objectID` 変数はリンクの一意の ID を提供します。これは、[Activity Map](/help/analyze/activity-map/overview.md) のレポートをより正確にするために使用します。頻繁に変更されるリンクがページ上にある場合は、`s_objectID` 変数を使用して一意のリンクの場所を Activity Map に知らせ、必要に応じてデータを正しくグループ化できます。

Activity Mapの精度が組織にとって重要な場合、Adobeでは、サイト上のリンクの `onClick` しいイベントに `s_objectID` 変数を含めることをお勧めします。

## Adobe Analytics拡張機能を使用したオブジェクト ID

Adobe Analytics 拡張機能には、この変数を使用する専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurementの s_objectID と Analytics 拡張機能のカスタムコードエディター

`s_objectID` はグローバル変数で、Analytics トラッキングオブジェクトとは独立して動作します（デフォルトで `s`）。この変数の有効な値は、100 バイトまでの任意の文字列です。この変数が定義されていない場合、Activity Mapはリンクテキストをリンクの識別情報として使用します。

この変数は、通常、HTML リンクの `onClick` イベントで設定されます。

```HTML
<a href="https://example.com" onClick="s_objectID='Example identifier';">Example link</a>
```

>[!NOTE]
>
> JavaScript ステートメントを終了するセミコロンは必ず含めてください。Activity Map が機能するには、セミコロンが必要です。

## 使用例

`s_objectID` 変数は、Activity Map レポートの精度を高めたい場合に役立ちます。

### 高度に動的なコンテンツからのリンクの集計

ニュースサイトや頻繁にアイテムを回転させる小売サイトなど、非常に動的なコンテンツを持つサイトもあります。Activity Map ではデフォルトでリンク URL を識別子として使用するので、リンクが頻繁に変更されるページで最もクリックされる領域を理解するのは困難です。これらのリンク内で `s_objectID` を使用する場合、Activity Map は、参照先の URL に関係なく、集計できるリンクを認識します。

```HTML
<a href="story1.html" onClick="s_objectID='Top left link';">Story 1</a>
<a href="story2.html" onClick="s_objectID='Top center link';">Story 2</a>
<a href="story3.html" onClick="s_objectID='Top right link';">Story 3</a>
```

リンクが指す場所や、これらのリンクを変更する頻度に関係なく、Activity Map は、`s_objectID` の値に基づいてデータを集計します。

### ページ上でリンクを別々に維持する

一部のサイトには、異なる場所の同じ場所を指すリンクがあります。例えば、サイトのヘッダーとフッターの両方にあるホームページへのリンクを指定します。これらのリンクは同じ URL なので、Activity Map はそのデータを集計します。`s_objectID` 変数を使用して区切ることができます。

```HTML
<a href="index.html" onClick="s_objectID='Header home link';">Example link in Header</a>
<a href="index.html" onClick="s_objectID='Footer home link';">Example link in Footer</a>
```

リンクが同じ URL を指している場合でも、Activity Mapはレポートでそれらを正しく区別するために `s_objectID` 変数を使用できます。
