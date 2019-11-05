---
description: Dynamic Tag Management を使用して Adobe Analytics をデプロイする場合の変数に関するフィールドの説明と情報です。
keywords: Dynamic Tag Management, グローバル変数, サーバー変数, evar, prop, 動的変数プレフィックス, 動的変数
seo-description: Dynamic Tag Management を使用して Adobe Analytics をデプロイする場合の変数に関するフィールドの説明と情報です。
seo-title: グローバル変数
solution: Experience Cloud, Analytics, Dynamic Tag Management
title: グローバル変数
uuid: d759320a-96ee-4073-b5fd-5257b7033003
translation-type: tm+mt
source-git-commit: 2fc1a01aced4cf2b165b46353418fbee9b83bee5

---


# グローバル変数

Dynamic Tag Management を使用して Adobe Analytics をデプロイする場合の変数に関するフィールドの説明と情報です。

これらの変数は、ページ型ルールのすべてのビーコンによって起動します。同様のことを実現する別の方法として、[ページ型ルール](/help/implement/c-implement-with-dtm/c-rules/t-rules-page-conditions.md)セットをすべてのページで起動させることもできます。これらの変数は、[ダイレクト型ルール](/help/implement/c-implement-with-dtm/c-rules/t-rules-direct-conditions.md)と[イベント型](/help/implement/c-implement-with-dtm/c-rules/t-rules-event-conditions.md)ルールでは実行されない可能性があります 。

## グローバル変数 - フィールドの説明 {#section_2917F62FCC8D43F982B2612A702DEF81}

**[!UICONTROL *`Property`*]**／![](assets/settings_gear.png) **[!UICONTROL ／ツールを編集]**／**[!UICONTROL グローバル変数]**

| 要素 | 説明 |
|--- |--- |
| サーバー | 事前に定義済みの変数により、Adobe Analytics のサーバーディメンションが設定されます。「[ページ変数](/help/implement/js-implementation/c-variables/page-variables.md)」を参照してください。 |
| eVar | [eVar 変数](/help/implement/js-implementation/c-variables/page-variables.md)は、カスタムコンバージョンレポートを作成するために使用します。 |
| prop | [Prop 変数](/help/implement/js-implementation/c-variables/page-variables.md)は、カスタムトラフィックレポートを作成するために使用します。 |
| 動的変数プレフィックス | 値の先頭に付ける特別なプレフィックスです。デフォルトのプレフィックスは「D=」です。「[動的変数](/help/implement/js-implementation/c-variables/dynvars-overview.md)」を参照してください。 |
