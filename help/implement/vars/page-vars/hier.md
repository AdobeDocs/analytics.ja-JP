---
title: hier
description: Adobe Analytics に階層変数を実装します。
feature: Variables
exl-id: 72bdab8f-a001-4ada-b5e2-453a8e3f24a6
source-git-commit: f435453f655caef89460de42ebecf489b021dc47
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 62%

---

# hier

>[!IMPORTANT]
>
> この変数は廃止され、Analysis Workspace で使用できるディメンションではありません。アドビでは、[eVar](evar.md) と分類の使用をお勧めします。

階層変数は、サイトの構造を確認できるカスタム変数です。アドビでは、実装で最大 5 つの階層変数をサポートします。

この変数は、サイト構造に 3 つ以上のレベルを持つサイトの場合に有効です。例えば、メディアサイトにスポーツセクションへの 4 つのレベル（`Sports`、`Local Sports`、`Baseball` および `Team name`）があるとします。誰かが野球ページを訪問すると、スポーツ、ローカルスポーツおよび野球のすべてのレベルにその訪問が反映されます。

実装で階層を使用する前に、各階層をレポートスイートの設定で設定してください。

## Web SDK を使用する階層

階層は [Adobe Analyticsにマッピング済み](https://experienceleague.adobe.com/docs/analytics/implementation/aep-edge/variable-mapping.html?lang=ja) XDM フィールドの下 `_experience.analytics.customDimensions.hierarchies.hier1` から `_experience.analytics.customDimensions.hierarchies.hier5`.

## Adobe Analytics拡張機能を使用する階層

階層は、Analytics 拡張機能の設定時（グローバル変数）またはルールで設定できます。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用して、
2. 目的のタグプロパティをクリックします。
3. 「[!UICONTROL ルール]」タブに移動し、目的のルールをクリックします（またはルールを作成します）。
4. 「[!UICONTROL アクション]」で、既存の「[!UICONTROL Adobe Analytics - 変数を設定]」アクションをクリックするか、「+」アイコンをクリックします。
5. 「[!UICONTROL 拡張機能]」ドロップダウンを「Adobe Analytics」に設定し、「[!UICONTROL アクションタイプ]」を「[!UICONTROL 変数を設定]」に設定します。
6. を [!UICONTROL 階層] 」セクションに入力します。

階層値は、静的な文字列に設定することも、データ要素を参照することもできます。 また、目的の区切り文字を設定することもできます。 ここで設定した区切り文字が、レポートスイートの設定で設定した区切り文字と一致していることを確認します。

## AppMeasurement および Analytics 拡張機能のカスタムコードエディターの s.hier1 ～ s.hier5

各階層は、組織固有のカスタム値を含む文字列です。 最大長は 255 バイトです。255 バイトを超える値は、アドビに送信する際に自動的に切り捨てられます。

セクション名には区切り文字を使用しないようにしてください。例えば、セクションの 1 つで `Coach Griffin, Jim` を呼び出す場合は、コンマ以外の区切り文字を選択します。変数の制限の合計は 255 バイトです。区切り文字は、`||` や `/|\` のように複数の文字で構成することもできます（複数の文字で構成すると、変数値で使用される可能性が低くなります）。

```js
s.hier1 = "Toys|Boys 6+|Legos|Super Block Tub";

s.hier3 = "Sports/Local Sports/Baseball";
```
