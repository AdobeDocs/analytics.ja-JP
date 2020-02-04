---
title: getTimeParting
description: 特定のアクションが実行される時間を測定します。
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Adobeプラグイン：getTimeParting

> [!IMPORTANT] このプラグインは、Adobe Analyticsからより多くの価値を引き出すのに役立つ、アドビコンサルティングによって提供されます。 アドビカスタマーケアは、インストールやトラブルシューティングを含め、このプラグインに対するサポートを行いません。 このプラグインに関するヘルプが必要な場合は、貴社のアカウントマネージャーにお問い合わせください。 担当コンサルタントとのミーティングを設定できます。

このプ `getTimeParting` ラグインを使用すると、サイトで測定可能なアクティビティが発生した時間の詳細を取り込むことができます。 このプラグインは、指定した日付範囲で繰り返し可能な時間の除算で指標を分類する場合に役立ちます。 例えば、すべての日曜日とすべての木曜日など、2つの異なる曜日間のコンバージョン率を比較できます。 また、すべての朝とすべての晩など、1日の期間を比較することもできます。

Analysis Workspaceは、このプラグインとは少し異なる形式の、標準搭載された同様のディメンションを提供します。 詳細につ [いては、『Analyzeユーザガイド](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md) 』の「時間分割ディメンション」を参照してください。 組織によっては、Analysis Workspaceの標準のディメンションで十分であると見なされる場合があります。

> [重要] ：このプラグインのバージョン4.0以降は、以前のバージョンとは大きく異なります。 アドビでは、このプラグインを「最初から」実装することを強くお勧めします。 バージョン4.0より前のプラグインを参照するコードは、このプラグインの現在のバージョンと互換性がありません。

## Adobe Experience Platform Launch Extensionを使用してプラグインをインストールする

アドビでは、最も一般的に使用されるプラグインを使用できる拡張機能を提供しています。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. 「拡張子」タブ [!UICONTROL に移動し] 、「カタログ」ボタンをクリッ [!UICONTROL クします] 。
1. Common Analytics Plugins  Extensionのインストールと公開
1. プラグインを使用する起動ルールに対して、次の設定を含むアクションを追加します。
   * 拡張子：共通のAnalyticsプラグイン
   * アクションタイプ：addProductEvarの初期化
1. ルールへの変更を保存して発行します

## カスタムコードエディターの起動を使用したプラグインのインストール

プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. 目的のプロパティをクリックします。
1. 「拡張」タブ [!UICONTROL に移動し] 、Adobe Analytics拡張機能の [!UICONTROL 下にある「設定] 」ボタンをクリックします。
1. 「カスタムコー [!UICONTROL ドを使用してトラッキングを設定] 」アコーディオンを展開すると、「エディターを開く  」ボタンが表示されます。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics拡張機能に公開します。

## AppMeasurementを使用したプラグインのインストール

Analyticsトラッキングオブジェクトをインスタンス化した後（を使用して）、AppMeasurementファイルの任意の場所に次のコードをコピーして貼り付 `s_gi`けます。 コードのコメントとバージョン番号を実装に保持しておくと、アドビは潜在的な問題のトラブルシューティングに役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeParting v6.2 */
var getTimeParting=function(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

このメソ `getTimeParting` ッドでは、次の引数を使用します。

**`t`**（オプション、推奨、文字列）:訪問者のローカル時間を変換するタイムゾーンの名前。  デフォルトはUTC/GMT時間です。 有効な[値の完全なリストについては、WikipediaのList of TZデータベースのタイムゾーン](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones)（英語）を参照してください。

一般的な有効値は次のとおりです。

* `"America/New_York"` 東部時代
* `"America/Chicago"` （中央時間）
* `"America/Denver"` 山岳地帯
* `"America/Los_Angeles"` 太平洋標準時

このメソッドを呼び出すと、次のように区切られたパイプ(`|`)を含む文字列が返されます。

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

ガーナはUTC/GMTタイムゾーン内です。  この例は、このような状況ではプラグイン引数が必要ないことを示しています。

### Internet Explorerブラウザーのアカウンティング

Internet Explorer訪問者から時間分割データを除外する場合は、次の例を使用します（IEブラウザから返される値は訪問者のローカル時間にのみ含まれる可能性があるため）。

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

...s.eVar10を「year=2020」に設定します。| month=August| date=31| day=金曜日| time=6:15 PM&quot;

次のコードを実行中…

```js
s.eVar10 = getTimeParting("America/Nome");
```

...s.eVar10を「year=2020」に設定します。| month=August| date=31| day=金曜日| time=6:15 AM&quot;

次のコード…

```js
s.eVar10 = getTimeParting("Asia/Calcutta");
```

...s.eVar10を「year=2020」に設定します。| month=August| date=31| day=金曜日| time=8:45 PM&quot;

次のコード…

```js
s.eVar10 = getTimeParting("Australia/Sydney");
```

...s.eVar10を「year=2020」に設定します。| month=9月| date=1| day=Saturday| time=1:15 AM&quot;

## バージョン履歴

### 6.2（2019年11月6日）

* 小規模なバグ修正
* 全体的なコードサイズの縮小

### 6.1（2018年11月26日）

* Internet Explorerブラウザーの問題を修正しました。 訪問者のローカル時間内でのみ時間を返すことができます。

### 6.0（2018年8月14日）

* 国際標準に合わせて完全に書き直す。 夏時間とすべてのタイムゾーンが適切に変換されるようになりました。

### 5.0（2018年4月18日）

* ポイントリリース（再コンパイル、コードサイズ小）
* 夏時間の開始日と終了日が自 `tpDST` 動的に検出されるようになったので、パラメータの必要性をなくしました。

### 4.0（2016年8月23日）

* 新しいソリューションを提供し、年、月、日付の情報を含むようになりました。
