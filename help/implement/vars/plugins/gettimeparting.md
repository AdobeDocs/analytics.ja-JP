---
title: getTimeParting
description: 特定のアクションが実行される時間を測定します。
feature: Variables
exl-id: 3fab36c8-a006-405a-9ef1-2547c2b36b0d
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '724'
ht-degree: 95%

---

# アドビプラグイン：getTimeParting

>[!IMPORTANT]
>
> このプラグインはアドビコンサルティングによって提供されており、Adobe Analytics からより多くの価値を引き出すのに役立ちます。アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートをおこないません。このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせになって、担当コンサルタントとのミーティングを手配してもらってください。

`getTimeParting` プラグインを使用すると、サイトで測定可能なアクティビティが発生した時間の詳細を取り込むことができます。このプラグインは、指定した日付範囲で繰り返し可能な時間の除算で指標を分類する場合に役立ちます。例えば、すべての日曜日とすべての木曜日など、2 つの異なる曜日間のコンバージョン率を比較できます。また、すべての朝とすべての晩など、1 日の時間を比較することもできます。

Analysis Workspace は、このプラグインとは少し異なる形式の、標準搭載された同様のディメンションを提供します。詳細については、『Analyze ユーザーガイド』の[時間分割ディメンション](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md)を参照してください。組織によっては、Analysis Workspace の標準のディメンションで十分であると見なされる場合があります。

>[!IMPORTANT]
>
>このプラグインのバージョン 4.0 以降は、以前のバージョンとは大きく異なります。アドビでは、このプラグインを「最初から」実装することを強くお勧めします。バージョン 4.0 より前のプラグインを参照するコードは、このプラグインの現在のバージョンと互換性がありません。

## Web SDK またはAdobe Analytics拡張機能を使用したプラグインのインストール

アドビでは、最も一般的に使用されるプラグインを使用できる拡張機能を提供しています。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用して、
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「[!UICONTROL カタログ]」ボタンをクリックします。
1. [!UICONTROL Common Analytics Plugins] 拡張機能をインストールして公開します。
1. まだ「Initialize Plug-ins」というルールを作成していない場合は、次の設定を使用してルールを作成します。
   * Condition：なし
   * Events：Core – 読み込まれたライブラリ（ページ上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * Extension：Common Analytics Plugins
   * Action Type：Initialize getTimeParting
1. ルールに対する変更を保存して発行します。

## カスタムコードエディターを使用したプラグインのインストール

プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. にログインします。 [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) Adobe ID 資格情報を使用して、
1. 目的のプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、Adobe Analytics 拡張機能の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
1. 「[!UICONTROL カスタムコードを使用してトラッキングを設定]」アコーディオンを展開すると、「[!UICONTROL エディターを開く]」ボタンが表示されます。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics 拡張機能に公開します。

## AppMeasurement を使用したプラグインのインストール

Analytics トラッキングオブジェクトをインスタンス化（[`s_gi`](../functions/s-gi.md) を使用）した後、AppMeasurement ファイルの任意の場所に次のコードをコピーして貼り付けます。実装時のコードのコメントとバージョン番号を記録しておくと、アドビが潜在的な問題のトラブルシューティングをおこなう際に役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeParting v6.3 (No Prerequisites Needed) */
function getTimeParting(t){var c=t;if("-v"===t)return{plugin:"getTimeParting",version:"6.3"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c){a=b;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.getTimeParting="6.3");c=document.documentMode?void 0:c||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:c,minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`getTimeParting` 関数では、次の引数を使用します。

**`t`**（オプション、推奨、文字列）：訪問者のローカル時間を変換するタイムゾーンの名前。デフォルトは UTC／GMT 時間です。有効な値の完全なリストについては、Wikipedia の [List of TZ database time zones](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)（英語）を参照してください。

一般的な有効値は次のとおりです。

* `"America/New_York"`（東部時間）
* `"America/Chicago"`（中央時間）
* `"America/Denver"`（山岳地帯）
* `"America/Los_Angeles"`（太平洋標準時間）

この関数を呼び出すと、パイプ（`|`）で区切られた次を含む文字列が返されます。

* 現在の年
* 現在の月
* 日
* 曜日
* 現在の時刻（AM/PM）

## 例

```js
// Use the following code if the visitor resides in Paris, France
s.eVar8 = getTimeParting("Europe/Paris");

// Use the following code if the visitor resides in San Jose, California
s.eVar17 = getTimeParting("America/Los_Angeles");

// Use the following code if the visitor resides in Ghana.
// Note that Ghana is in GMT time, the default time zone that the plug-in uses with no argument
s.eVar22 = getTimeParting();

// Internet Explorer only returns the visitor's local time. Use this conditional statement to accommodate IE visitors
if(!document.documentMode) s.eVar39 = getTimeParting("America/New_York");
else s.eVarX = "Internet Explorer Visitors";

// Given a visitor from Denver Colorado visits a site on August 31, 2020 at 9:15 AM
// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=6:15 PM"
s.eVar10 = getTimeParting("Europe/Athens");

// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=6:15 AM"
s.eVar11 = getTimeParting("America/Nome");

// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=8:45 PM"
s.eVar12 = getTimeParting("Asia/Calcutta");

// Returns the string value "year=2020 | month=September | date=1 | day=Saturday | time=1:15 AM"
s.eVar13 = getTimeParting("Australia/Sydney");
```

## バージョン履歴

### 6.3 （2021 年 3 月 19 日（PT））

* コンテキストデータとしてバージョン番号を追加しました。

### 6.2（2019 年 11 月 5 日（PT））

* 小規模なバグ修正
* 全体的なコードサイズの縮小

### 6.1（2018 年 11 月 26 日（PT））

* Internet Explorer ブラウザーでの問題を修正しました。訪問者のローカル時間内でのみ時間を返すことができます。

### 6.0（2018 年 8 月 14 日（PT））

* 国際標準に合わせて完全に書き直しました。夏時間とすべてのタイムゾーンが適切に変換されるようになりました。

### 5.0（2018 年 4 月 17 日（PT））

* ポイントリリース（再コンパイル、コードサイズ縮小）
* 夏時間の開始日と終了日を自動的に検出するようにして `tpDST` パラメーターの必要性をなくしました。

>[!CAUTION]
>
>このプラグインの以前のバージョンは、今後のすべての年数に対応するわけではありません。このプラグインの以前のバージョンを使用する場合は、JavaScript のエラーやデータ損失を防ぐため、Adobeでは最新バージョンにアップグレードすることを強くお勧めします。このプラグインをアップグレードできない場合は、プラグインコードの`s._tpdst`変数に将来の適切な年が含まれていることを確認してください。

### 4.0（2016 年 8 月 22 日（PT））

* 新しいソリューションを提供し、年、月、日付の情報を含むようになりました。
