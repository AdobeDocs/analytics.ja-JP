---
title: s_objectID
description: Activity Map で、サイト上の一意のリンクを識別します。
exl-id: 7c0cb750-2bfe-41ca-ab27-30dda4b3a7fa
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '401'
ht-degree: 100%

---

# s_objectID

`s_objectID` 変数はリンクの一意の ID を提供します。これは、[Activity Map](/help/analyze/activity-map/activity-map.md) のレポートをより正確にするために使用します。頻繁に変更されるリンクがページ上にある場合は、`s_objectID` 変数を使用して一意のリンクの場所を Activity Map に知らせ、必要に応じてデータを正しくグループ化できます。

Activity Map の精度が組織にとって重要な場合は、サイト上のリンクの `onClick` イベントに `s_objectID` 変数を含めることをお勧めします。詳しくは、『Analyze ユーザーガイド』の [Activity Map リンクトラッキングの使用例](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-use-case.md)を参照してください。

## Adobe Experience Platform Launch のオブジェクト ID

Launch にはこの変数を使用するための専用のフィールドはありません。AppMeasurement 構文に従って、カスタムコードエディターを使用します。

## AppMeasurement および Launch カスタムコードエディターの s_objectID

`s_objectID` はグローバル変数で、Analytics トラッキングオブジェクトとは独立して動作します（デフォルトで `s`）。この変数の有効な値は、100 バイトまでの任意の文字列です。この変数を定義していない場合、Activity Map はリンク URL をリンクの識別子として使用します。

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

リンクが同じ URL を指している場合でも、Activity Map は `s_objectID` 変数を使用して、レポートでリンクを正しく区別できます。
