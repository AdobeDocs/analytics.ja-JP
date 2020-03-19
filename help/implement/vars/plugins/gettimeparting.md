---
title: getTimeParting
description: 特定のアクションが実行される時間を測定します。
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Adobeプラグイン：getTimeParting

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すために、アドビコンサルティングから提供されています。 アドビカスタマーケアは、インストールやトラブルシューティングを含む、このプラグインのサポートを提供しません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを手配できます。

このプ `getTimeParting` ラグインを使用すると、サイトで測定可能なアクティビティが発生した時間の詳細を取り込むことができます。 このプラグインは、指定した日付範囲で、繰り返し可能な時間の除算で指標を分類する場合に役立ちます。 例えば、すべての日曜日とすべての木曜日など、2つの異なる曜日間のコンバージョン率を比較できます。 また、すべての朝とすべての晩など、1日の期間を比較することもできます。

Analysis Workspaceは、このプラグインとは少し異なる形式の、標準搭載の同じディメンションを提供します。 詳細につ [いては、Analyzeユーザガイドの](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md) 「時間分割ディメンション」を参照してください。 組織によっては、Analysis Workspaceの標準のディメンションで十分であると見なされます。

> [重要] ：このプラグインのバージョン4.0以降は、以前のバージョンとは大きく異なります。 アドビでは、このプラグインを「一から」実装することを強くお勧めします。 バージョン4.0より前のプラグインを参照するコードは、このプラグインの現在のバージョンと互換性がありません。

## Adobe Experience Platform Launch Extensionを使用してプラグインをインストールする

アドビでは、最もよく使用されるプラグインを使用できる拡張機能を提供しています。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. タブに移動し [!UICONTROL Extensions] 、ボタンをクリックしま [!UICONTROL Catalog] す。
1. 拡張機能のインストールと公 [!UICONTROL Common Analytics Plugins] 開
1. まだ設定していない場合は、「Initialize Plug-ins」というラベルの付いたルールを次の設定で作成します。
   * 条件：なし
   * イベント：コア — ライブラリ読み込み済み（ページの上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * 拡張子：共通のAnalyticsプラグイン
   * アクションタイプ：getTimePartingの初期化
1. ルールに対する変更を保存して発行します。

## カスタムコードエディターの起動を使用したプラグインのインストール

プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. タブに移動し [!UICONTROL Extensions] 、Adobe Analytics拡張機能の下 [!UICONTROL Configure] にあるボタンをクリックします。
1. アコーディオ [!UICONTROL Configure tracking using custom code] ンを展開し、ボタンを表示 [!UICONTROL Open Editor] します。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics拡張機能に公開します。

## AppMeasurementを使用したプラグインのインストール

次のコードを、Analyticsトラッキングオブジェクトのインスタンス化（を使用）後に、AppMeasurementファイルの任意の場所にコピーして貼り付 [`s_gi`](../functions/s-gi.md)けます。 導入時にコードのコメントとバージョン番号を保持すると、アドビは潜在的な問題のトラブルシューティングに役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeParting v6.2 */
var getTimeParting=function(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `getTimeParting` ッドでは、次の引数を使用します。

**`t`** （オプション、推奨、文字列）:訪問者のローカル時間を変換するタイムゾーンの名前。  デフォルトはUTC/GMT時刻です。 有効な [値の完全なリストについては、WikipediaのTZデータベースのタイムゾーンのリスト](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) （英語のみ）を参照してください。

一般的な有効な値は次のとおりです。

* `"America/New_York"` 東部時代
* `"America/Chicago"` （中央時間）
* `"America/Denver"` 山の時間
* `"America/Los_Angeles"` 太平洋標準時

このメソッドを呼び出すと、次のようにパイプで区切られた文字列が返さ`|`れます。

* 現在の年
* 現在の月
* 日
* 曜日
* 現在の時刻(AM/PM)

## 呼び出しの例

### 特定のタイムゾーンの例

クライアントがフランスのパリにある場合は、次のサンプルコードを使用します。

```js
s.eVarX = getTimeParting("Europe/Paris");
```

クライアントがカリフォルニア州サンノゼにある場合：

```js
s.eVarX = getTimeParting("America/Los_Angeles");
```

依頼人がアフリカのガーナの国にいる場合：

```js
s.eVarX = getTimeParting();
```

ガーナはUTC/GMTのタイムゾーンの範囲内です。  この例は、このような状況ではプラグイン引数が必要ないことを示しています。

### Internet Explorerブラウザーのアカウント

Internet Explorer訪問者から時間分割データを除外する場合は、次の例を使用します（IEブラウザから返される値は訪問者のローカル時間にのみ含まれるので）。

```js
if(!document.documentMode) s.eVarX = getTimeParting("America/New_York");
else s.eVarX = "Internet Explorer Visitors";
```

### 呼び出しの結果

コロラド州デンバーからの訪問者が2020年8月31日午前9時15分にサイトを訪問した場合、

次のコードを実行しています…

```js
s.eVar10 = getTimeParting("Europe/Athens");
```

...s.eVar10を「year=2020」に設定します。| month=8月| date=31| day=金曜日| time=6:15 PM&quot;

次のコードを実行中…

```js
s.eVar10 = getTimeParting("America/Nome");
```

...s.eVar10を「year=2020」に設定します。| month=8月| date=31| day=金曜日| time=6:15 AM&quot;

次のコード…

```js
s.eVar10 = getTimeParting("Asia/Calcutta");
```

...s.eVar10を「year=2020」に設定します。| month=8月| date=31| day=金曜日| time=8:45 PM&quot;

次のコードは…

```js
s.eVar10 = getTimeParting("Australia/Sydney");
```

...s.eVar10を「year=2020」に設定します。| month=9月| date=1| day=Saturday| time=1:15 AM&quot;

## バージョン履歴

### 6.2（2019年11月6日）

* 小さなバグ修正
* 全体的なコードサイズの削減

### 6.1（2018年11月26日）

* Internet Explorerブラウザーの修正。 訪問者のローカル時間でのみ、時間を返すことができます。

### 6.0（2018年8月14日）

* 国際基準に合わせた完全な書き直し。 夏時間とすべてのタイムゾーンが適切に変換されるようになりました。

### 5.0（2018年4月18日）

* ポイントリリース（再コンパイル、コードサイズが小さい）
* 夏時間の開始日/終了日が自 `tpDST` 動的に検出されるようになったため、パラメータの必要性をなくしました。

### 4.0（2016年8月23日）

* 新しいソリューションを提供し、年、月、日付の情報を含めます。
