---
description: 処理ルールは、コンテキストデータ変数の値を prop および eVar に移動するために使用されます。
subtopic: Processing rules
title: コンテキストデータ変数の eVar へのコピー
feature: Admin Tools
uuid: 1beaec4c-71e9-49ce-b154-78408cc532a3
exl-id: f52c2c6c-da3d-43d6-be13-92d0820c93b4
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '231'
ht-degree: 100%

---

# コンテキストデータ変数の eVar へのコピー

処理ルールは、コンテキストデータ変数の値を prop および eVar に移動するために使用されます。処理ルールがないと、Analytics にレポートが出力されないため、コンテキストデータ変数は無意味となります。

[!UICONTROL コンテキスト変数]リストには、過去 30 日間にレポートスイートへ送信されたすべての変数が含まれます。コンテキストデータ変数名を把握しているが、現在のレポートスイートに送信していない場合、値を追加するには、変数名を入力して、「**[!UICONTROL 変数名コンテキストデータを追加]**」をクリックします。

![追加](assets/add-context-variable.png)

次の例では、`search_term`コンテキストデータ変数を使用し、その値を `eVar3` に配置します。

![設定](assets/set-context-data.png)

上記の例は、生成する eVar が少数の場合に適しています。組織に数百のコンテキストデータ変数があり、各変数に独自の eVar が必要な場合は、条件文を使用できます。多数の条件文を単一の処理ルールに含めることができるので、処理ルールの上限である 150 個の範囲内で、レポートスイート内のすべての eVar を生成できます。

次の例では、`testhierarchy` が設定されている場合にのみ、コンテキストデータ変数 `testhierarchy` を使用して `prop7` を生成します。

![条件付き](assets/add-conditional.png)

コンテキストデータ変数の実装について詳しくは、実装ユーザーガイドの[コンテキストデータ変数](/help/implement/vars/page-vars/contextdata.md)を参照してください。
