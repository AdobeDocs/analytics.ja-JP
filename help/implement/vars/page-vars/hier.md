---
title: hier
description: （廃止）Adobe Analyticsで階層変数を実装する。
feature: Appmeasurement Implementation
exl-id: 72bdab8f-a001-4ada-b5e2-453a8e3f24a6
role: Admin, Developer
TQID: https://experienceleague.adobe.com/ngX4oPKy0XWEb-9xLpxSAdoAqZmfsMM8rbEH2-llHX4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 354
ht-degree: 98%

---

# hier

>[!IMPORTANT]
>
>この変数は廃止されており、Analysis Workspace で使用できるディメンションではありません。 アドビでは、代わりに [eVar](evar.md) と分類を使用することをお勧めします。

階層変数は、サイトの構造を確認できるカスタム変数です。 アドビでは、実装で最大 5 つの階層変数をサポートします。

この変数は、サイト構造に 3 つ以上のレベルを持つサイトの場合に有効です。 例えば、メディアサイトにスポーツセクションへの 4 つのレベル（`Sports`、`Local Sports`、`Baseball` および `Team name`）があるとします。 誰かが野球ページを訪問すると、スポーツ、ローカルスポーツおよび野球のすべてのレベルにその訪問が反映されます。

実装で階層を使用する前に、レポートスイートの設定で各階層を設定していることを確認してください。

## Web SDK を使用する階層

階層は XDM フィールドの `xdm._experience.analytics.customDimensions.hierarchies.hier1` から `xdm._experience.analytics.customDimensions.hierarchies.hier5` に [Adobe Analytics でマッピング](/help/implement/aep-edge/xdm-var-mapping.md)されます。

## Adobe Analytics 拡張機能を使用した階層

階層は、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. [!UICONTROL 拡張機能]ドロップダウンリストを Adobe Analytics に設定し、[!UICONTROL アクションタイプ]を[!UICONTROL 変数を設定]に設定します。
6. [!UICONTROL 階層]セクションを見つけます。

階層値を静的な文字列に設定するか、データ要素を参照できます。 また、目的の区切り文字を設定することもできます。 ここで設定した区切り文字が、レポートスイートの設定で設定した区切り文字と一致することを確認します。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.hier1 ～ s.hier5

各階層は、組織に固有のカスタム値を含む文字列です。 最大長は 255 バイトです。255 バイトを超える値は、アドビに送信する際に自動的に切り捨てられます。

セクション名には区切り文字を使用しないようにしてください。 例えば、セクションの 1 つで `Coach Griffin, Jim` を呼び出す場合は、コンマ以外の区切り文字を選択します。 変数の制限の合計は 255 バイトです。 区切り文字は、`||` や `/|\` のように複数の文字で構成することもできます（複数の文字で構成すると、変数値で使用される可能性が低くなります）。

```js
s.hier1 = "Toys|Boys 6+|Legos|Super Block Tub";

s.hier3 = "Sports/Local Sports/Baseball";
```
