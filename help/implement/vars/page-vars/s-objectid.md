---
title: s_objectID
description: Activity mapで、サイト上の一意のリンクを識別します。
translation-type: tm+mt
source-git-commit: c7d596be4f70c820039725be6a5fddc8572156d9

---


# s_objectID

変数は `s_objectID` リンクの一意の識別子を提供します。 これは、 [Activity mapのレポートをより正確にするた](/help/analyze/activity-map/activity-map.md) めに使用します。 頻繁に変更されるリンクがページ上にある場合は、変数を使用して一意のリンクの場所をActivity mapに知らせ、必要に応じてデータを正しくグループ化できます。 `s_objectID`

Activity mapの精度が組織にとって重要な場合は、サイト上のリンクのイベン `s_objectID` トに変数を含め `onClick` ることをお勧めします。 詳しく [は、Analyzeユーザーガイドの](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-use-case.md) 「Activity mapリンクトラッキングの使用例」を参照してください。

## Adobe Experience Platform LaunchのオブジェクトID

この変数を使用する専用のフィールドが「起動」にありません。 AppMeasurement構文に従って、カスタムコードエディターを使用します。

## AppMeasurementのs_objectIDおよびカスタムコードエディターの起動

この変 `s_objectID` 数はグローバル変数で、Analyticsトラッキングオブジェクトとは独立して動作し`s` ます（デフォルト）。 この変数の有効な値は、100バイトまでの任意の文字列です。 この変数を定義していない場合、Activity mapはリンクURLをリンクの識別子として使用します。

この変数は、通常、HTMLリンクのイベ `onClick` ントで設定されます。

```HTML
<a href="https://example.com" onClick="s_objectID='Example identifier';">Example link</a>
```

> [!NOTE] JavaScriptステートメントを終了するセミコロンは必ず含めてください。 Activity mapが機能するには、セミコロンが必要です。

## 使用例

この変 `s_objectID` 数は、Activity mapレポートの精度を高めたい場合に役立ちます。

### 高度に動的なコンテンツからのリンクの集計

ニュースサイトや頻繁にアイテムを回転させる小売サイトなど、非常に動的なコンテンツを持つサイトもあります。 Activity mapではデフォルトでリンクURLを識別子として使用するので、リンクが頻繁に変更されるページで最もクリックされる領域を理解するのは困難です。 これらのリンク内で `s_objectID` を使用する場合、Activity mapは、参照先のURLに関係なく、集計できるリンクを認識します。

```HTML
<a href="story1.html" onClick="s_objectID='Top left link';">Story 1</a>
<a href="story2.html" onClick="s_objectID='Top center link';">Story 2</a>
<a href="story3.html" onClick="s_objectID='Top right link';">Story 3</a>
```

リンクが指す場所や、これらのリンクを変更する頻度に関係なく、Activity mapは、の値に基づいてデータを集計しま `s_objectID`す。

### ページ上でリンクを別々に維持する

一部のサイトには、異なる場所の同じ場所を指すリンクがあります。 例えば、サイトのヘッダーとフッターの両方にあるホームページへのリンクを指定します。 これらのリンクは同じURLなので、Activity mapはそのデータを集計します。 変数を使用して区切ることがで `s_objectID` きます。

```HTML
<a href="index.html" onClick="s_objectID='Header home link';">Example link in Header</a>
<a href="index.html" onClick="s_objectID='Footer home link';">Example link in Footer</a>
```

リンクが同じURLを指している場合でも、Activity mapはこの変数を使用して、レポ `s_objectID` ートでリンクを正しく区別できます。
