---
description: getTimeParting プラグインは、時間、曜日および週末と平日の値をカスタム変数に入力します。Analysis Workspace では、初期設定で時間分割のディメンションを利用できます。このプラグインは、他の Analytics ソリューション（Analysis Workspace 以外）で時間分割のディメンションが必要な場合に使用します。
keywords: Analytics Implementation
subtopic: Plug-ins
title: getTimeParting
topic: Developer and implementation
uuid: 74f696a3-7169-4560-89b2-478b3d8385e1
translation-type: tm+mt
source-git-commit: 73d20b23e38bc619c156c418c95096a94d2fdfce

---


# getTimeParting

getTimePartingプラグインは、測定可能なアクティビティがサイトで発生した時間の詳細を取り込むための完全な分析ソリューションを提供します。

指定した日付範囲で、繰り返し可能な時間の除算で指標を分類する場合は、getTimePartingプラグインを使用します。  例えば、getTimePartingプラグインを使用すると、2つの異なる曜日（例：全日曜日と全木曜日）、2つの異なる期間（例：全朝と全朝）、または2つの後続の分（例：全午前10:00インスタンスと午前10:01）の間のコンバージョン率を比較できます。インスタンス)を使用します。

[!DNL Analysis Workspace] には、このプラグインが提供するものと少し異なる方法でフォーマットされた、標準搭載のサイズと似たものが用意されて [います](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.html)（ここを参照）。  アドビのコンサルティング部門では、このヘルプの残りの部分を読んで、このプラグインがニーズに合った方法でデータを提供するかどうかを判断することをお勧めします。

特定の日付範囲にわたって、繰り返し可能な時間の除算によって指標を分類する必要がない場合は、getTimePartingプラグインを使用する必要はありません。  また、時間分割ディメンシ [!DNL Analysis Workspace] ョンが十分にある場合は、このプラグインを実装する必要はありません。

>[!CAUTION] getTimePartingプラグインのバージョン4.0以降が提供するソリューションは、プラグインの以前のバージョンとは大きく異なります。  4.0より前のバージョンからアップグレードする場合は、ソリューションを「最初から」実装する必要があります。  つまり、プラグインから提供されたデータを保持する新しいeVar（1つのeVar）を設定し、このドキュメントをよく読んでから、ソリューションを実装する必要があります。

>[!CAUTION] また、このバージョンのプラグインは、Microsoft Internet Explorer *ブラウザー* との完全な互換性がありませんが、Microsoft edgeブラウザーとの完全な互換性があります。   Internet Explorerを使用する訪問者は、指定したタイムゾーンに変換するのではなく、ローカルのタ *イム* ゾーンでのみ時刻を提供できます。  Internet Explorerブラウザーのデータを含まず、その存在を説明するソリューションの例を以下に示します。

> [!NOTE]後述の説明では、実際のサイトに合わせてデータ収集コードを変更する必要があります。変更は、サイトでのデータ収集に影響が及ぶ可能性があるので、[!DNL Analytics] の使用と導入の経験がある開発者のみがおこなうようにしてください。

> [!WARNING] 必ず、実稼働環境にデプロイする前にすべてのプラグイン実装をテストし、データ収集が期待どおりに動作することを確認してください。

## 前提条件

なし

## 導入方法

* 次のコードをAppMeasurementコードのプラグインセクション内の任意の場所にコピー&amp;ペーストします。

```function getTimeParting(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])}```

> [!NOTE] また、Adobe Launchなどのタグマネージャーを使用して、プラグインコードをAppMeasurementや他の解析ソリューションに接続する必要なく導入することもできます

* 以下に説明するように、doPlugins関数内、または時間分割データを取り込む必要がある他の場所でgetTimeParting関数を実行します

**渡す引数**

* t:(オ&#x200B;**プションですが推奨**、文字列)訪問者のローカル時間を変換するタイムゾーンの名前。  デフォルトは「Etc/GMT」、未設定の場合はUTC/GMT時間です。  入力す [る値の完全なリストは、https://en.wikipedia.org/wiki/List_of_tz_database_time_zones] にアクセスしてください。

一般的な値は次のとおりです。

* 東部時間の場合は「America/New_York」
* Central time用の「America/Chicago」
* 山岳部時間の「America/Denver」
* 太平洋標準時の「America/Los_Angeles」

## 戻り値

getTimePartingプラグインは、次を含む文字列を返します。

* 現在の年
* 現在の月
* 現在の日付（日）
* 現在の日（曜日）
* 現在の時刻（非軍事時刻）

上記の各項目はパイプ文字(&quot;|&quot;)で区切られます。

## 呼び出しの例

フランスのパリに住んでいて、eVar10(Adobe Analytics)を使用して時間分割データを取得する場合は、次のコードを使用します。

```s.eVar10 = getTimeParting("Europe/Paris")```

カリフォルニア州サンノゼに居住している場合は、次のコードを使用します。

```s.eVar10 = getTimeParting("America/Los_Angeles")```

アフリカのガーナ国にいる場合は、次のコードを使用します。

```s.eVar10 = getTimeParting();```

ガーナはUTC/GMTタイムゾーン内です。  この例は、このような状況ではプラグイン引数が必要ないことを示しています。

ニューヨークに住んでいて、Internet Explorer訪問者からのデータを含めない場合は、次のコードを使用します（IEブラウザーから返される値は訪問者のローカル時間にのみ指定できるため）。

```if(!document.documentMode) s.eVar10 = getTimeParting("America/New_York");```
```else s.eVar10 = "Internet Explorer Visitors";```

**呼び出しの結果**

コロラド州デンバーからの訪問者が2020年8月31日午前9時15分にサイトを訪問した場合、次のコードは…

```s.eVar10 = getTimeParting("Europe/Athens");```

...はs.eVar10を **year=2020に設定します| month=August| date=31| day=Monday| time=6:15 PM**

次のコード…

```s.eVar10 = getTimeParting("America/Nome");```

代わりに、s.eVar10を **year=2020に設定します。| month=August| date=31| day=Monday| time=6:15 AM**

次のコード…

```s.eVar10 = getTimeParting("Asia/Calcutta");```

代わりに、s.eVar10を **year=2020に設定します。| month=August| date=31| day=Monday| time=8:45 PM**

次のコード…

```s.eVar10 = getTimeParting("Australia/Sydney");```

代わりに、s.eVar10を **year=2020に設定します。| month=9月| date=1| day=Tuesday| time=1:15 AM**

## Adobe Analyticsの設定

Adobe Analyticsで時間分割データを取り込む場合は、次の特性を持つ新しいeVarを設定してください。

* 名前：時間分割
* 配分：最新（最後）
* 有効期限：訪問
* その他のすべての属性は、指定されたデフォルト値を使用します
