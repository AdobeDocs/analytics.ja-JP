---
description: AppMeasurement 3.x for ios
seo-description: AppMeasurement 3.x for iosのレガシードキュメント
seo-title: AppMeasurement 3.x for ios
solution: Analytics
subtopic: ブックマーク
title: AppMeasurement 3.x for ios
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 4907b2930d894525b93b02f743c095f824a61a3b

---


# AppMeasurement 3.x for iOS

*注意：このドキュメントには、AppMeasurementの以前のバージョン（特にiOS用バージョン3.x向け）に関するレガシー情報が含まれています。
現在のAppMeasurement実装について詳しくは、Javascript版AppMeasurementに[ついてを参照してください](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html)。*

*2018年3月16日AppMeasurement 3.x for iOSの最終更新日*

Adobe appMeasurement for iOSを使用すると、Adobe Experience cloudでネイティブのApple iPhoneおよびiPadアプリケーションの測定を行うことができます。

本書は二つの部分に分かれている。adobe Analyticsのエクスペリエンスを持つアナリスト向けの1つのセクションと、モバイルアプリの開発エクスペリエンスを持つiOS開発者向けの1つのセクションです。

**サポート対象バージョン**:iOS 4.3以降。

**すべてのAppMeasurementモバイルプラ**&#x200B;ットフォームのライブラリのダウンロード手順とリンクは、Developer Connectionの測定と最適化モバイルアプリケーションページで入手できます。 ライブラリをダウンロードするには、無料の Developer Connection アカウントまたは Reports &amp; Analytics ログインが必要です。ダウンロードリンクはログインしないと表示されません。

## アナリストクイックスタート

iOS ライブラリの実装、および標準的な実装に必要となるコードの追加に関する手順を説明します。カスタムイベントやその他のデータの送信方法を示す手順も含まれています。

アナリストとしてご使用の場合は、モバイルアプリケーションレポートをレポートスイートで有効にする必要があります。レポートの収集指標を追加したい場合は、どのようなコンテキストデータ変数をアプリケーションから送りたいかを開発者に詳しくお伝えください。例えば、ログイン後のユーザー名を収集するために、`myco.username` というコンテキストデータ変数にユーザー名を設定するように開発者に指示します。

### Analytics でのモバイルアプリケーションレポートの有効化

Analytics には、モバイルアプリのライフサイクル追跡機能を有効にするためのインターフェイスが用意されています。この追跡機能のマッピングによって、Analytics ではモバイルアプリケーションレポートが自動的に生成されます。

1. 管理コンソール／レポートスイート／設定の編集／モバイル管理／モバイルアプリケーションレポートを開きます。
1. 「モバイルアプリのライフサイクル追跡を有効にする」をクリックします。

これで、ライフサイクル指標が収集され、モバイルアプリケーションレポートが SiteCatalyst の レポートメニューに表示されます。

### 処理ルールを使用した追加の指標の収集

コンテキストデータを使用してその他のイベントやディメンションを送るには、そのデータを収集する処理ルールを設定する必要があります。

処理ルールを作成するには、組織内の担当者が認定を受ける必要があります。詳しくは、処理ルールに関するヘルプを参照してください。

処理ルールを有効にした後は、コンテキストデータ変数のコピーの例に、コンテキストデータのマッピングに必要となるプロセスが示されています。

### （オプション）オフライン追跡の有効化

デバイスがオフラインの場合にヒットを保存するには、レポートスイートでタイムスタンプを有効にする必要があります。

オフライン追跡を有効にした後、すべてのヒットにタイムスタンプを付ける必要があります。タイムスタンプのないヒットは収集されません。現在、同じレポートスイートで JavaScript と AppMeasurement からデータを収集している場合は、データの消失を防ぐためにモバイルデータのレポートスイートを個別に設定するか、s.timestamp 変数を使用して JavaScript からのデータにカスタムタイムスタンプを入れてください。

レポートスイートでタイムスタンプが有効になっているかどうかがわからない場合は、カスタマーケアにお問い合わせください。

## 開発者クイックスタート

iOSライブラリを実装し、測定データの送信を開始する手順を説明します。次に例を示します。

* ライブラリの取得
* プロジェクトへのライブラリの追加
* TrackingHelper の概要
* 実装


### ライブラリの取得

Developer Connection の「モバイルアプリケーションの測定と最適化￼」にアクセスして、Android ライブラリをダウンロードしてください。ダウンロードファイルを解凍すると、次のソフトウェアコンポーネントが展開されます。

* admsAppLibrary.jar：Android デバイスとシミュレーターで使用するように設計されたライブラリ。Android 2.0 以降が必要です。
* Examples\TrackingHelper.java：トラッキングコードをアプリケーションロジックから分離するように設計されたオプションのクラス。

### プロジェクトへのライブラリの追加

1. Eclipse IDE で、プロジェクト名を右クリックします。
1. Build Path（ビルドパス）／Add External Archives（外部アーカイブの追加）を選択します。
1. Select `admsAppLibrary.jar`.
1. 「Open（開く）」をクリックします。
1. プロジェクトを再度右クリックし、Build Path（ビルドパス）／Configure Build Path（ビルドパスを設定）を選択します。
1. 「Order and Export（順序とエクスポート）」タブをクリックします。
1. `admsAppLibrary.jar` が選択済みであることを確認します。

アプリケーションは、admsAppLibrary.jarライブラリからimport com.adobe.ADMSを使用してクラスやインターフェイスをインポートできます。*;

### アプリの権限の追加

AppMeasurement ライブラリでは、データの送信とオフラインのトラッキングコールの記録のために、次の権限が必要です。

* INTERNET
* ACCESS_NETWORK_STATE

To add these permissions, add the following lines to your AndroidManifest.xml file (in the application project directory):
`<uses-permission android:name="android.permission.INTERNET" />`
`<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />`

### TrackingHelper の概要

SDK には、TrackingHelper という追加のオプションクラスが含まれています。TrackingHelper を使用すると、測定コードをアプリケーションロジックから分離することができます。

例：アプリケーションで、各ログインを追跡するイベントを送信するとします。その場合、ログインコードの直後に次のコードを追加して、このイベントを送信することができます（コードについて詳しくは後述）。

```
Hashtable<String, Object> contextData = new Hashtable<String, Object>();
contextData.put("username", "username_value");
measure.trackEvents("event1", contextData);
```

このような直接的な方法でも問題ありませんが、アプリケーションの開発中、開発者に負荷をかけないようにこのコードを 1 か所に集約した方がよいでしょう。TrackingHelper がその配置先となります。TrackingHelper 内で、このコードを trackLogonEvent というメソッドの内部に配置できます。

```
public static void trackLogonEvent (String username_value) {
Hashtable<String, Object> contextData = new Hashtable<String, Object>();
contextData.put("username", username_value);
measure.trackEvents("event1", contextData);
}
```

これで、アプリケーションコード内で、trackLogonEvent を呼び出すだけでログオンイベントを追跡することができます。

TrackingHelper.trackLogonEvent("username");

アプリケーションコード内では、測定コールが 1 行だけになります。さらに、基本となる測定ロジックを変更する場合は、TrackingHelper を更新するだけで済みます。他の開発者がコードに変更を加える場合に、AppMeasurement ライブラリについて調査しなくても、定義済みの簡素化されたメソッドを使用できます。

1 ～ 2 分程度の設定が必要になりますが、新しい実装に対しては TrackingHelper を使用することをお勧めします。このガイドの以降の手順では、TrackingHelper を設定し、測定データの送信を開始するための手順について説明します。

アプリケーションのクラスファイルを含むディレクトリに TrackingHelper.java をコピーし、このファイルの上部にあるパッケージ名を、パッケージ構造（com.company.application）に合うように置き換えてください。TrackingHelper を使用せずに実装する場合は、TrackingHelper に含まれるサンプルをアプリケーションにコピーできます。

### 実装

1. TrackingHelper.java を開き、レポートスイート ID とトラッキングサーバーの情報を使用して TRACKING_RSID と TRACKING_SERVER を更新します。次に例を示します。

   ```
   private static final String TRACKING_RSID = "rsid";
   private static final String TRACKING_SERVER = "server";
   ```

   これらの値は必須であり、正しい値を指定しなければ測定が動作しません。これらの値がわからない場合は、SiteCatalyst のエキスパートにお問い合わせください。

2. configureAppMeasurement メソッドを探します。このメソッドを使って、SSL の有効化やオフライン追跡の有効化をはじめ、その他の設定の一括変更を行うことができます。ここでは、期待どおりの動作となるまで、debugLogging を有効にする行のコメントを解除します。

3. アプリケーションのルートアクティビティからの configureAppMeasurement のコールを追加します。

```
@Override
public void onCreate(Bundle savedInstanceState) {
super.onCreate(savedInstanceState);
setContentView(R.layout.main);
TrackingHelper.configureAppMeasurement(this);
}
```

カスタム指標の追跡を開始するのに必要となるコードはこれだけです。ただし、さらにコードを数行追加することで、起動、アップグレード、クラッシュ、日別ユーザー、月別ユーザーなどのライフサイクル指標を自動的に送信できるようになります。

難しい処理の実行はすべて AppMeasurement ライブラリが担当します。開発者が行う必要があるのは、アプリケーションの各 Activity クラスに 2 つのメソッドコールを追加することだけです。

### （推奨）ライフサイクルイベントの追跡

ライフサイクル追跡を有効にすると、アプリが起動されるたびに、1回のヒットが送信され、インストール、アップグレード、関与日数およびその他のライフサイクル指標が追跡されます。

ライフサイクルイベントの追跡を開始するには、次の例のように、アプリケーション内部の各 Activity に、onResume() メソッドと onPause() メソッドのコールを追加します。また、グローバルの Application コンテキストではなく、Activity または Service をコンテキストオブジェクトとして渡すことをお勧めします。

```
@Override
protected void onResume() {
super.onResume();
TrackingHelper.startActivity(this);
}
@Override
protected void onPause() {
super.onPause();
TrackingHelper.stopActivity();
}
```

これで作業は完了です。Android アプリケーションに基本的なライフサイクル追跡機能を実装できました。Web アナリストが、レポートの対象となる AppMeasurement 指標を処理するように SiteCatalyst を設定すると、SiteCatalyst レポートスイートにデフォルトのライフサイクル指標が反映されるようになります。

これをベースにして、以下の機能を追加できます。

* （オプション）カスタムイベントの追跡。TrackingHelper にカスタムメソッドを追加して、アプリケーションで測定するすべてのイベントを追跡します。ログオン、アプリケーション内での購入などを追跡するためのメソッドを追加できます。
* （オプション）アプリケーション状態の追跡。アプリケーション状態は、ページビューに似ています。この節では、TrackingHelper にカスタムメソッドを追加してアプリケーション状態を追跡する方法について説明しています。
* ビデオ測定クイックスタート. ビデオビュー、再生時間合計、最も人気のあるビデオなどのビデオ指標を追跡するためのコードを追加します。

### （オプション）カスタムイベントの追跡

カスタムイベントは、それぞれのアプリケーションに固有の成功指標です。ユーザーのログイン時、アプリケーション内部での購入の開始時、Facebook ページへのリンクのクリック時などにカスタムイベントを送信できます。追跡ヘルパークラスには、カスタムイベントの追跡方法を示す例が含まれています。このメソッドをテンプレートとして使用し、他のイベント追跡メソッドを追加することができます。

TrackingHelper.java に、カスタムのイベント追跡メソッドを次のように定義します。

```
public static void trackCustomEvents () {
Hashtable<String, Object> contextData = new Hashtable<String, Object>();
contextData.put("contextKey", "value");
measure.trackEvents("event1, event2", contextData);
}
```

コードのどこからでも、このメソッドを呼び出すことでカスタムイベントを追跡できます。

`TrackingHelper.trackCustomEvents();`

以上のプロセスを使用して、必要な数のイベント追跡メソッドを追加します。「TrackingHelper の概要」には、ログインイベントを追跡するためのサンプルのメソッドが記載されています。

### （オプション）アプリケーション状態の追跡

追跡ヘルパークラスには、アプリケーション状態の追跡方法を示す例も含まれています。カスタム状態の追跡は、イベントの追跡と非常に似ています。異なるのは、trackEvents の代わりに trackAppState メソッドを使用することだけです。

```
measure.trackAppState("name", contextData);
```

レポートの観点から見ると、trackAppState はページビュー数を増分しますが、trackEvents は増分しません。

## ビデオ測定クイックスタート

ビデオ測定については、SiteCatalyst でのビデオの測定ガイドで説明しています。ビデオ測定の一般的なプロセスは、AppMeasurement のすべてのプラットフォームでほぼ同一です。このクイックスタートでは、開発者のタスクに関する基本的な概要とコード例を示します。

アプリケーションとビデオの追跡には、同じライブラリ admsAppLibrary.jar を使用します。ドキュメントでは、プラットフォーム間の一貫性を確保するために、追跡用のメソッドをメディアモジュールと呼んでいます。

メディアモジュールを使用するには、測定インスタンスを設定しておく必要があります。

Android でビデオの追跡を実装するには、次のタスクを実行します。

* プレーヤーイベントの SiteCatalyst 変数へのマッピング
* マイルストーン、セグメントおよびコール頻度の設定
* プレーヤーイベントの追跡

### プレーヤーイベントの SiteCatalyst 変数へのマッピング

ビデオ測定を設定するには、ビデオ追跡の対象として選択した SiteCatalyst イベントおよび eVar を、コンテキストデータ変数にマッピングする必要があります。詳しくは、SiteCatalyst のビデオ設定を参照してください。

Web アナリストからビデオ実装のワークシートを入手する必要があります。このワークシートには、ビデオデータの受信用に設定された SiteCatalyst 変数の一覧が含まれています。

* ビデオ名(eVar):eVar2
* ビデオ名(prop):prop2
* セグメント(eVar):eVar3
* コンテンツタイプ(eVar):eVar1
* ビデオ時間（イベント）:event3
* ビデオビュー（イベント）:event1
* ビデオ完了（イベント）:event7
* ビデオセグメントビュー（イベント）:event2

1. 実装で追加したコードの後に次のコードを追加し、変数名の部分を選択した SiteCatalyst 変数例に置き換えます。

   ```
   ADMS_MediaMeasurement mediaMeasure = ADMS_MediaMeasurement.sharedInstance();
   Hashtable<String, Object> contextDataMapping = new Hashtable<String, Object>();
   contextDataMapping.put("a.media.name", "eVar2,prop2");
   contextDataMapping.put("a.media.segment", "eVar3");
   contextDataMapping.put("a.contentType", "eVar1"); //note that this is not in the .media
   namespace
   contextDataMapping.put("a.media.timePlayed", "event3");
   contextDataMapping.put("a.media.view", "event1");
   contextDataMapping.put("a.media.segmentView", "event2");
   contextDataMapping.put("a.media.complete", "event7");
   mediaMeasure.ContextDataMapping = contextDataMapping;
   ```

2. マイルストーン、セグメントおよびコール頻度の設定.

3. プレーヤーイベントの追跡.


### マイルストーン、セグメントおよびコール頻度の設定

マイルストーンは、ビデオが特定のポイントまで再生されたときにイベントを送信するための機能です。セグメントは、ビデオを複数のセクションに分割し、より細かく追跡を行うための機能です。コール頻度は、特定の時間間隔で測定コールを送信するための機能です。詳しくは、「ビデオ指標」を参照してください。

### マイルストーンのマッピング

全体の長さに対する割合または経過秒数に基づいて、マイルストーンを定義できます。次の例では、マイルストーンを全体の長さに対する割合として定義しています。2 分のビデオの場合、次のコードでは、30 秒、60 秒および 90 秒の時点でマイルストーンイベントが送信されます。

```
Hashtable<String, Object> milestoneMapping = new Hashtable<String, Object>();
milestoneMapping.put("25", "event4");
milestoneMapping.put("50", "event5");
milestoneMapping.put("75", "event6");
contextDataMapping.put("a.media.milestones", milestoneMapping);
```


### オフセットマイルストーンのマッピング

次の例では、ビデオの開始時点からの経過秒数によってマイルストーンを定義しています。2 分のビデオの場合、次のコードでは、ビデオの全体の長さにかかわらず、20 秒、40 秒および 60 秒の時点でマイルストーンイベントが送信されます。

```
Hashtable<String, Object> offsetMilestoneMapping = new Hashtable<String, Object>();
offsetMilestoneMapping.put("20", "event8");
offsetMilestoneMapping.put("40", "event9");
offsetMilestoneMapping.put("60", "event10");

contextDataMapping.put("a.media.offsetMilestones", offsetMilestoneMapping);
```

### 例

```
//get sharedInstance
ADMS_MediaMeasurement mediaMeasure = ADMS_MediaMeasurement.sharedInstance();

//Track By Milestones:
mediaMeasure.trackMilestones = "25,50,75";

// track Milestones & segmentByMilestones:
mediaMeasure.trackMilestones = "25,50,75";
mediaMeasure.segmentByMilestones = true;

// track by seconds:
mediaMeasure.trackSeconds = 15;

// track Milestones & segmentByMilestones & seconds:
mediaMeasure.trackMilestones = "25,50,75";
mediaMeasure.segmentByMilestones = true;
mediaMeasure.trackSeconds = 15;

// track offsetMilestones & segmentByOffsetMilestones:
mediaMeasure.trackOffsetMilestones = "15,30,45,60,75,90";
mediaMeasure.segmentByOffsetMilestones = true;

// track offsetMilestones:
mediaMeasure.trackOffsetMilestones = "5,15,45";
```

### プレーヤーイベントの追跡

ビデオを測定するには、プレーヤーでイベントが発生したタイミングをメディアモジュールに通知するコード（open、play、stop および close の各メソッドを使用）を追加する必要があります。例えば、ユーザーがビデオの再生を開始したときに、play メソッドを呼び出して、メディアモジュールで視聴秒数のカウントを開始する必要があります。

また、ユーザーがビデオを一時停止した場合には、stop を呼び出して、カウントを一時停止する必要があります。これは、一般的に、プレーヤーで公開されているイベントハンドラーを使用して実行します。

次に例を示します。

ロード：open と play を呼び出します。

一時停止：stop を呼び出します。例えば、ユーザーが 15 秒後にビデオを一時停止したときは、stop("Video1",15) を呼び出します。

バッファー：ビデオのバッファリング中に stop を呼び出します。再生が再開されたときに play を呼び出します。

再開：play を呼び出します。例えば、既に 15 秒間再生されたビデオを再開するときは、s.play("Video1",15) を呼び出します。

スクラブ（スライダー）：ユーザーがビデオスライダーをドラッグしたとき、stop を呼び出します。ユーザーがビデオのスライダーを離したときに、play を呼び出します。

終了：stop を呼び出してから、close を呼び出します。例えば、100 秒のビデオの最後で、stop("Video1",100) を呼び出した後、close("Video1") を呼び出します。

以上を実行するために、メディアプレーヤーイベントハンドラーから呼び出すことができる 4 つのカスタム関数を定義します。プレーヤーから各種のパラメーターが open、play、stop および close に渡されます。次の擬似コードに、この処理を示します。

```
function startMovie(){
mediaMeasure.open(mediaName,mediaLength,mediaPlayerName);
playMovie();
}
/*Call on video resume from pause and slider release*/
function playMovie(){
mediaMeasure.play(mediaName,mediaOffset);
}
/*Call on video pause and slider grab*/
function stopMovie(){
mediaMeasure.stop(mediaName,mediaOffset);
}
/*Call on video end*/
function endMovie(){
stopMovie();
mediaMeasure.close(mediaName);
Video Measurement Quick Start 12
```

## ライフサイクル指標

以下のワークシートに、自動ライフサイクル追跡が有効な場合に測定される指標とディメンションの一覧を示します。

### ライフサイクル指標およびディメンション

設定された場合、ライフサイクル指標は、コンテキストデータパラメーターで Analytics に送信され、mbox 呼び出しのたびにパラメーターが Target に送信され、シグナルとして Audience Management に送信されます。Analytics および Target は同じ形式を使用しますが、Audience Management は、各指標に異なるプレフィックスを使用します。

Analytics の場合、ライフサイクルトラッキングコールのたびに送信されたコンテキストデータは、最初の列にリストされた指標またはディメンションを使用して、自動的にキャプチャされ、レポートされます（説明列に記載されている場合を除く）。

| 指標 | Analyticsコンテキスト | Analytics Context Audience Managerシグナルの説明 | Data/Target Parameter |
|--- |--- |--- |--- |
| 初回起動 | a.InstallEvent | c_a_InstallEvent | インストール後（または再インストール後）の最初の起動時にトリガーされます。 |
| アップグレード | a.UpgradeEvent | c_a_UpgradeEvent | アップグレード後の最初の実行時にトリガーされます（バージョン番号が変更されるたびに）。 |
| 日別関与ユーザー数 | a.DailyEngUserEvent | c_a_DailyEngUserEvent | 特定の日にアプリケーションが使用された場合にトリガーされます。 |
| 月別アクションを実行したユーザー | 月別アクションを実行したユーザー | a.MonthlyEngUserEvent | 特定の月内にアプリケーションが使用された場合にトリガーされます。 |
| 起動 | a.LaunchEvent | c_a_LaunchEvent | クラッシュおよびインストールを含め、実行のたびにトリガーされます。 | 起動：ライフサイクルセッションのタイムアウトを超えた場合に、バックグラウンドからの再開時にもトリガーされます。 |
| クラッシュ | a.CrashEvent | c_a_CrashEvent | アプリケーションが正常に終了しなかった場合にトリガーされます。イベントは、クラッシュ後の次回のアプリ起動時に送信されます（quit が正常に呼び出されなかった場合にアプリがクラッシュしたと見なされます）。 |
| 前回のセッションの長さ | a.PreviousSessionLength | Cc_a_PreviousSessionLength | 集計された前回のセッションの合計の長さ（秒）。 |

*注意：日別関与ユー&#x200B;**ザー数と月別関**与ユーザー数は&#x200B;****、Analytics指標に自動的には保存されません。 これらの指標を取得するためのカスタムイベントを設定する処理ルールを作成する必要があります。*

### ディメンション

| 指標 | Analytics コンテキストデータ／Target パラメーター | Analytics Context Audience Managerシグナル | 説明 |
|--- |--- |--- |--- |
| インストール日 | a.InstallDate | c_a_InstallDate | インストール後の初回起動日。MM/DD/YYYY |
| アップグレード | a.UpgradeEvent | c_a_UpgradeEvent | アップグレード後の最初の実行時にトリガーされます（バージョン番号が変更されるたびに）。 |
| アプリケーション ID | a.AppID | c_a_AppID | アプリケーションの名前とバージョンを次の形式で格納します。`[AppName] [BundleVersion]`例：myapp 1.1。 |
| 初回使用からの日数 | a.DaysSinceFirstUse | c_a_DaysSinceFirstUse | 初回起動時からの日数。 |
| 月別関与ユーザー数 | 月別アクションを実行したユーザー | a.MonthlyEngUserEvent | 特定の月内にアプリケーションが使用された場合にトリガーされます。 |
| 起動 | a.LaunchEvent | c_a_LaunchEvent | クラッシュおよびインストールを含め、実行のたびにトリガーされます。 | 起動：ライフサイクルセッションのタイムアウトを超えた場合に、バックグラウンドからの再開時にもトリガーされます。 |
| クラッシュ | a.CrashEvent | c_a_CrashEvent | アプリケーションが正常に終了しなかった場合にトリガーされます。イベントは、クラッシュ後の次回のアプリ起動時に送信されます（quit が正常に呼び出されなかった場合にアプリがクラッシュしたと見なされます）。 |
| 前回のセッションの長さ | a.PreviousSessionLength | Cc_a_PreviousSessionLength | 集計された前回のセッションの合計の長さ（秒）。 |
| 前回使用からの日数 | a.DaysSinceLastUse | c_a_DaysSinceLastUse | 前回使用時からの経過日数。 |
| 曜日 | a.DayOfWeek | c_a_DayOfWeek | アプリケーションが起動された曜日を表す数値。 |
| 時間帯 | a.HourOfDay | c_a_HourOfDay | アプリケーションが起動された時刻を測定します。24 時間形式です。利用のピーク時間を判定するために使用します。 |
| オペレーティングシステムのバージョン | a.OSVersion | c_a_OSVersion | OS のバージョン。 |
| 前回アップグレードからの日数 | a.DaysSinceLastUpgrade | c_a_DaysSinceLastUpgrade | アプリのバージョン番号が変更されてからの日数。 |
| 前回アップグレードからの起動回数 | a.LaunchesSinceUpgrade | c_a_LaunchesSinceUpgrade | アプリのバージョン番号が変更されてからの起動回数。 |
| デバイス名 | a.DeviceName | c_a_DeviceName | デバイス名が格納されます。 | iOS：iOS デバイスを識別するコンマ区切りの 2 桁の文字列。最初の番号は通常、デバイスの世代を表します。次の番号は通常、デバイスファミリー内の個々のメンバーのバージョン番号です。一般的なデバイス名の一覧については、「iOS デバイスのバージョン」を参照してください。 |
| 通信事業者名 | a.CarrierName | c_a_CarrierName | デバイスによって提供された携帯キャリアの名前が格納されます。 |
| 解像度 | a.Resolution | c_a_Resolution | 実際のピクセル単位での幅 x 高さ |

*注意：前回ア&#x200B;**ップグレードからの日数**、前回ア&#x200B;**ップグレードからの起動回数******、通信事業者名はAnalytics変数に自動的には保存されません。 You must create a processing rule to copy these values to an Analytics variable for reporting.*

## コンテキストデータ

コンテキストデータは、データを収集サーバーに送信するための推奨される方法です。

値を prop と eVar に明示的に割り当てる代わりに、コンテキストデータ変数を使用して、SiteCatalyst でマッピングされる名前と値のペアを送信できます。これらのキーと値のペアに基づいて、イベントを設定し、値をeVarとpropにコピーし、追加の条件文を実行できます。 この方法によって、コードを更新しなくても異なるレポートスイートの設定をサポートできるようになります。

コンテキストデータを送信する方法は 2 つあります。PersistentContextData オブジェクトに直接設定されたすべてのコンテキストデータは、メソッドが呼び出されるたびに送信されます。また、1 回のトラッキングコールだけで送信されるコンテキストデータは、そのコールのパラメーターとして渡すことができます。

### 永続的なコンテキストデータ

永続的なコンテキストデータにセットされた値は、サーバーコールが実行されるたびに送信されます。次の例では、"key" と "value" が、すべての trackAppState コールと共に送信されます。

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.setPersistentContextData(contextData);
measure.trackAppState("state1");
measure.trackAppState("state2");
measure.trackAppState("state3");
```

### 1 回のコールのコンテキストデータ

1 回のコールのみでコンテキストデータを送信するには、コンテキストデータをトラッキングコール（trackAppState、trackEvents など）のパラメーターとして送信します。

次の例では、"key" と "value" が、3 回の trackAppState コールごとに送信されます。ただし、"key2" と "value2" は、2 回目の trackAppState コールのみで送信されます。

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.setPersistentContextData = contextData;
Hashtable<String, Object> contextDataState = new HashTable<String,Object>();
contextDataState.put("key2", "value2");
measure.trackAppState("state1");
measure.trackAppState("state2", contextDataState);
measure.trackAppState("state3");
```

## 設定変数

アプリケーションの起動時に次の変数が設定されます。:

*注意：ReportSuiteIDとtrackingServerを除くすべての設定変数はオプションです。*

**共有インスタンス**

測定コールを送信する前に、測定ライブラリで呼び出すメソッドごとに、ライブラリのインスタンスを取得する必要があります。

```
ADMS_Measurement measure = ADMS_Measurement.sharedInstance(((Activity)
context).getApplication());
```

*注意：設定変数はプライベート変数です。これらの変数の値を変更するには、get メソッドと set メソッドを使用してください。*

### 設定変数

**reportSuiteIDs**:（必須）追跡する1つまたは複数のレポートスイート（マルチスイートタギング）。 複数のレポートスイートを追跡するには、各レポートスイート名をコンマで区切ったリストを渡します。

この変数は 1 回のコールでオーバーライドすることができません。永続的な値を変更する必要があります。

構文：

```
String getReportSuiteIDs()
void setReportSuiteIDs(String reportSuiteIDs)
```

例:

`measure.setReportSuiteIDs("rsid");`

マルチスイートタギング:
`measure.setReportSuiteIDs("rsid1, rsid2");`

**trackingServer**:（必須）収集サーバーを識別します。

この変数は、「http://」または「https://」プロトコルプレフィックスなしで、トラッキングサーバードメインに設定される必要があります。プロトコルプレフィックスは、ssl 変数に基づいてライブラリで自動的に処理されます。

ssl が true の場合、このサーバーとの安全な接続が確立されます。ssl が false の場合、このサーバーとの安全でない接続が確立されます。

この変数は 1 回のコールでオーバーライドすることができません。永続的な値を変更する必要があります。

構文：

```
String getTrackingServer()
void setTrackingServer(String trackingServer)
```

例:

`measure.setTrackingServer("metrics.corp1.com");`

**visitorID**:デフォルト：uuidUnique各訪問者の識別子。 カスタムの visitorID を設定しない場合は、一意の visitorID が生成されます。

固有の visitorID を設定する必要がある場合を除き、デフォルトを使用することをお勧めします。カスタムの visitorID を設定すると、ライフサイクル追跡を使用する場合に訪問回数が重複する可能性があります。この問題を回避するには、アプリケーション測定を設定する前に訪問者 ID を設定してください。

**characterSet**:初期設定はUTF-8です。

構文：

```
String getCharSet()
void setCharSet(String charSet)
```

例:
`[measure.setCharacterSet("UTF-8");`

**currencyCode**：デフォルトはnone（レポートスイート用に定義された値が使用される）

Android アプリケーション内で追跡する購入イベントや通貨イベントの通貨コード。

構文：

```
String getCurrencyCode()
void setCurrencyCode(String currencyCode)
```

例:
`measure.setCurrencyCode("USD");`

**lifecycleSessionTimeout**:初期設定は5分です

アプリケーションの起動が新しいセッションであると見なされるまでの経過時間を秒数で指定します。このタイムアウトは、アプリケーションがバックグラウンドに移行し、再びアクティブになる場合にも適用されます。アプリケーションがバックグラウンドになっている時間はセッションの長さには含まれません。

構文：

```
int getLifecycleSessionTimeout()
void setLifecycleSessionTimeout(int sessionLength)
```

例:

`measure.setLifecycleSessionTimeout(600); //10 minute session`

**ssl**:初期設定はfalseです。

SSL（HTTPS）を介した測定データの送信設定を有効（true）または無効（false）にします。この変数は 1 回のコールでオーバーライドすることができません。永続的な値を変更する必要があります。

構文：

`void setSSL(boolean ssl)`

例:

`measure.setSSL(true);`

**debugLogging** デフォルトはfalse

出力コンソールでのデバッグ情報とライブラリのバージョンの表示を有効（true）または無効（false）にします。デフォルトでは、この変数は false です。この変数は 1 回のコールでオーバーライドすることができません。永続的な値を変更する必要があります。

構文：

`void setDebugLogging(boolean debugLogging)`

例:

`measure.setDebugLogging(true);`

## トラッキング変数

**共有インスタンス**

測定コールを送信する前に、測定ライブラリで呼び出すメソッドごとに、ライブラリのインスタンスを取得する必要があります。

```
ADMS_Measurement measure = ADMS_Measurement.sharedInstance(((Activity)
context).getApplication());
```

*注意：設定変数はプライベート変数です。これらの変数の値を変更するには、get メソッドと set メソッドを使用してください。*

### 永続的なトラッキング変数

**Evar**:指定したeVarに指定した値を設定します。 この eVar は、値を空の文字列に設定するか clearVars を呼び出してクリアするまでは、すべてのトラッキングコールと共に送信されます。

構文：

`void setEvar(int evarNum, String evarValue)`

例：`measure.setEvar(1, "value");`

**Prop**:指定したpropに指定した値を設定します。 この prop は、値を空の文字列に設定するか clearVars を呼び出してクリアするまでは、すべてのトラッキングコールと共に送信されます。

構文：

`void setProp(int propNum, String propValue)`

例：

`measure.setProp(1, "value");`

**Hier**:指定したhier変数に指定した値を設定します。 この hier 変数は、値を空の文字列に設定するか clearVars を呼び出してクリアするまでは、すべてのトラッキングコールと共に送信されます。

構文：

`void setHier(int hierNum, String hierValue)`

例：

`measure.setHier(1, "value");`


**ListVar**:指定したlistVarに指定した値を設定します。 この listVar は、値を空の文字列に設定するか clearVars を呼び出してクリアするまでは、すべてのトラッキングコールと共に送信されます。

構文：

`void setListVar(int listNum, String listValue)`

例：

`measure.setListVar(1, "value");`

**purchaseID**:purchaseIDは、SiteCatalystで注文が複数回カウントされないようにするために使用します。

サイトで購入イベントを使用する場合は、purchaseID 変数を使用して、この購入に一意の ID を割り当てる必要があります。

`measure.setPurchaseID("unique_id");`

**transactionID**:統合データソースでは、トランザクションIDを使用して、オフラインデータをオンライントランザクション（リードやオンラインで生成された購入など）に結び付けます。

アドビに送信する個別の transactionID は、それぞれトランザクションに関するオフライン情報のデータソースへのアップロードを準備するために記録されます。

`measure.setTransactionID("unique_id");`

**appState**:（ページ名）アプリ状態に対して指定された値は、ページ名変数に格納されます。

`measure.setAppState("state");`

**channel**:measure.setChannel("mobile");

**appSection**:アプリセクションに指定した値は、サーバー変数に格納されます。

構文：

`void setAppSection(String Section)`

例：`measure.setAppSection("news");`

**campaign**

構文：

`void setCampaign(String Campaign)`

例：

`measure.setCampaign("112233");`

**products**

構文：

```
void setProducts(String Products)
// example Products string: Category;Product[,Category;Product]
```

例：

`measure.setProducts("Running;Shoe");`

**events**

構文：

`void setEvents(String Event) //comma-delimited list`

例：

`measure.setEvents("event1, event2");`

**geoState**

構文：

`void setGeoState(String GeoState)`

例：

`measure.setGeoState("UT");`

**geoZip**

構文：

`void setGeoZip(String GeoZip)`

例：

`measure.setGeoZip("12345");`

**永続的なコンテキストデータ**:永続的なコンテキストデータに配置された値は、サーバーコールが実行されるたびに送信されます。 1 回のコールのみでコンテキストデータを送信するには、contextData ハッシュテーブルをトラッキングコール（trackAppState、trackEvents など）のパラメーターとして送信します。

例：

```
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
measure.setPersistentContextData(contextData);
```

コンテキストデータを参照してください。

**linkTrackVars**:変数名のコンマ区切りリスト。このリストは、リンクトラッキングを制限する変数の現在のセットです。 linkTrackVars を定義していない場合、AppMeasurement for Android では、trackLink コールで、定義済みのすべての変数が送信されます。

構文：

`void setLinkTrackVars(String Vars) //comma-delimited list`

例：

`measure.setLinkTrackVars("eVar1, prop1");`

**linkTrackEvents**:イベントのコンマ区切りのリスト。現在のイベントセットはリンクの追跡が制限されます。 linkTrackEvents を定義していない場合、AppMeasurement for Android では、trackLink コールで、すべてのイベントが送信されます。

構文：

`void setLinkTrackEvents(String Events) //comma-delimited list`

例：

`measure.setLinkTrackEvents("event1, event2");`

## メソッド

この節では、Android ライブラリが提供するメソッドの一覧を記載します。

**共有インスタンス**

測定コールを送信する前に、測定ライブラリで呼び出すメソッドごとに、ライブラリのインスタンスを取得する必要があります。

```
ADMS_Measurement measure = ADMS_Measurement.sharedInstance(((Activity)
context).getApplication());
```

### 初期設定

このメソッドは必須の変数を設定します。他のメソッドの前に呼び出す必要があります。

**configureMeasurement**:このメソッドは、アプリケーション測定を開始するために必要な2つのパラメーターを設定するために使用します。 サーバーコールを送信する前に、このメソッドを使用して測定オブジェクトの reportSuiteIDs および trackingServer の値を設定する必要があります。

構文：

`void configureMeasurement(String reportSuiteIDs, String trackingServer)`

例:

`measure.configureMeasurement("my_rsid", "my_tracking_server");`

### イベントおよび状態の追跡

以下は、カスタムイベントおよびアプリケーション状態の追跡に使用する主要なメソッドです。

**trackAppState**:アプリケーション内のアプリケーション状態を追跡する場合に推奨される方法です。 appState に指定した値は、サーバーコールのページ名変数として表示されます。appState 文字列は、次回のコールまで持ち越されないので、呼び出すたびに指定する必要があります。

このコールの 2 つめの引数で指定されるコンテキストデータは、persistentContextData のすべての値に追加され、コールと共に送信されます。persistentContextData に設定した値のみが次回のコールまで維持されます。

構文：

`void trackAppState(string AppStateName)`

例:

`measure.trackAppState("state");`

```
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
measure.trackAppState("state", contextData);
```

**trackEvents**:アプリケーション内のイベントを追跡する場合は、この方法をお勧めします。 trackEventsはtrackAppStateに似ていますが、ページ名ではなくイベントを送信します。 イベントはコンマ区切りの文字列で指定します。events 文字列は、次回のコールまで持ち越されないので、呼び出すたびに指定する必要があります。

このメソッドは、内部でtrackLinkURLを呼び出します。この際、linkURLはnilに、linkTypeは"o"に設定され、linkNameはアプリケーションIDを使用して設定されます。

つまり、linkTrackVars と linkTrackEvents が、trackEvents へのコールに適用されます。

このコールの 2 つめの引数で指定されるコンテキストデータは、persistentContextData のすべての値に追加され、コールと共に送信されます。persistentContextData に設定した値のみが次回のコールまで維持されます。

構文：

`void trackEvents(string Events)`

例:

`measure.trackEvents("event1");`

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.trackEvents("event1", contextData);
```

**trackLink メソッドを使用するときの注意事項**

trackEvents では、内部で trackLink が呼び出されます。この際、linkURL は null に、linkType は "o" に設定され、linkName はアプリケーション ID を使用して設定されます。この処理は、ページビュー（状態ビュー）のカウントがイベントを送信するたびに増加するのを防ぐために行われます。

trackLink を直接呼び出して、linkTrackVars および linkTrackEvents の値を設定すると、これらの変数およびイベントの制約が TrackEvents に適用されます。つまり、これらのリストに定義されている変数およびイベントのみが、TrackEvents によって送信されます。このような制約を trackEvents に適用したくない場合は、linkTrackVars および linkTrackEvents を null に設定してください。

### 高度な追跡（track と trackLink）

以下のメソッドには、追加の追跡オプションが用意されています。これらのオプションによって、prop や eVar などの SiteCatalyst 変数を直接設定できます。これらのオプションは、既存の SiteCatalyst の実装を使用するお客様、または他の SiteCatalyst の実装を詳細に理解しているお客様が使用してください。

`track` および `trackLink` は主要な測定メソッドであり、複数のプラットフォームにおける Adobe Measurement Library のすべてのバージョンに実装されます。モバイルアプリケーションの追跡を行うほとんどの状況で、trackAppState メソッドおよび trackEvents メソッドを使用するほうが、track および trackLink を直接呼び出すよりも簡単です。

ページビュー追跡（track）およびリンク追跡（trackLink）では、値（null、空、ゼロ以外の値）を持つすべての永続的な変数が送信されます。track または trackLink を呼び出す前に、必要に応じてすべての変数をリセットするか、空にする必要があります。

*注意：最新のアプリケーションのマルチスレッドの特性により、今後のコールと共に送信する永続的な変数値を設定することは推奨されません（setEvar、setProp、setHier、SetListVarおよびsetPersistentContextDataを使用）。 例えば、変数値が複数のスレッドで設定されている場合、トラッキングコールが行われると、値の状態が一貫しない可能性があります。 この問題を回避するには、各トラッキングコールと共にコンテキストデータを渡し、処理ルールで変数値を設定することをお勧めします。

**メソッドの説明**

**track**:標準のページビューと、測定オブジェクトに設定された追加の変数を収集サーバーに送信します。

track を呼び出すたびに、測定オブジェクトに定義されたすべての永続的なデータ（clearVars の説明に記載されているもの）と、そのコールのみに指定したすべての contextData または変数が送信されます。値がセットされた後者は、対応する永続的な変数に設定された値を上書きします。

構文：

```
void track()
void track(Hashtable<String, Object> contextData)
void track(Hashtable<String, Object> contextData, Hashtable<String, Object>
variables)
```

例:

`measure.track();`

```
measure.setEvar(1, "evar1value");
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
measure.track(contextData);
```

```
//set an eVar
measure.setEvar(1, "evar1value");
//contextData
Hashtable contextData = new Hashtable<String, Object>();
contextData.put("key", "value");
//variable overrides
Hashtable variableOverrides = new Hashtable<String, Object>();
variableOverrides.put("evar2", "evar2value");
//sends eVar1, eVar2 (set in overrides), and context data
measure.track(contextData, variableOverrides);
```

**trackLink**:カスタム、ダウンロード、または離脱リンクのデータを、値を持つtrackconfig変数と共にAdobeデータ収集サーバーに送信します。

ページビューをカウントアップすべきではないアクティビティを追跡する場合に、trackLink を使用します。

構文：

```
void trackLink(String linkURL, String linkType, String linkName,
Hashtable<String, Object> contextData, Hashtable<String, Object> variables)
```

**linkURL**：クリックされた URL を識別します。URL を指定しない場合は、名前が使用されます。これは、お使いの Android アプリケーションから Web ページにリンクするときにのみ使用してください。それ以外の場合は、このパラメーターでは null を渡します。

**linkType**：URL または名前を表示するリンクレポートを識別します。次の値がサポートされています。
* "o"（カスタムリンク）
* "d"（ファイルダウンロード）
* "e"（離脱リンク）

**linkName**：リンクレポートに表示される名前。名前を指定しない場合は、レポートに URL が表示されます。

データを収集するには、linkURL と linkName のいずれかのパラメーターを指定する必要があります。これらのパラメーターの1つ、コンテキストデータまたは追加の変数を使用しない場合は、nullを値として渡します。

例:

`measure.trackLink("url", "o", "name", contextData, null);`

**setEvar**:指定したeVarに指定した値を設定します。 この eVar は、値を空の文字列に設定するか clearVars を呼び出してクリアするまでは、すべてのトラッキングコールと共に送信されます。

構文：

`void setEvar(int evarNum, String evarValue)`

**setProp**:指定したpropに指定した値を設定します。 この prop は、値を空の文字列に設定するか clearVars を呼び出してクリアするまでは、すべてのトラッキングコールと共に送信されます。

構文：

`void setProp(int propNum, String propValue)`

**setHier**:指定したhier変数に指定した値を設定します。 この変数は、値を空の文字列に設定するか clearVars を呼び出してクリアするまでは、すべてのトラッキングコールと共に送信されます。

構文：

`void setHier(int hierNum, String hierValue)`

**setListVar**:指定したlistVarに指定した値を設定します。 この変数は、値を空の文字列に設定するか clearVars を呼び出してクリアするまでは、すべてのトラッキングコールと共に送信されます。

構文：

`void setListVar(int listNum, String listValue)`

**setPersistentContextData**:永続的なコンテキストデータに配置された値は、サーバーコールが実行されるたびに送信されます。 1 回のコールのみでコンテキストデータを送信するには、contextData ハッシュテーブルをトラッキングコール（trackAppState、trackEvents など）のパラメーターとして送信します。

```
Hashtable<String, Object> contextData = new HashTable<String,Object>();
contextData.put("key", "value");
measure.setPersistentContextData(contextData);
```

コンテキストデータを参照してください。

**clearVars**:オブジェクト上の次の変数から値を削除します。

```
props
eVars
heirs
listVars
events
PersistentContextData
purchaseID
transactionID
appState
channel
appSection
campaign
products
geoZip
geoState
linkTrackVars
linkTrackEvents
```

構文：

`void clearVars()`

例:
`measure.clearVars();`

**オフライン追跡**

*注意：オフラインでの AppMeasurement を有効にするには、レポートスイートでタイムスタンプを有効にする必要があります。*

以下の変数を使用して、アプリケーションがオフラインのときに測定コールを格納できます。オフラインでの AppMeasurement を有効にするには、レポートスイートでタイムスタンプを有効にする必要があります。この変更を行った後、すべてのヒットにタイムスタンプを付加する必要があります。タイムスタンプのないヒットは破棄されます。現在、同じレポートスイートで JavaScript と AppMeasurement からデータを収集している場合は、データの消失を防ぐために、AppMeasurement のオフラインのレポートスイートを個別に設定することをお勧めします。

オフラインでの AppMeasurement を有効にすると、次のような動作になります。
* アプリケーションによりサーバーコールが送信されますが、データの送信が失敗します。
* AppMeasurement により、現在のヒットのタイムスタンプが生成されます。
* AppMeasurement ではヒットデータがバッファーされ、データの消失を防ぐために、バッファーされたヒットデータが永続的なストレージにバックアップされます。

後続のヒットがあるたびに、または offlineThrottleDelay で定義された間隔で、AppMeasurement により、元のヒット順を維持しながら、バッファーされたヒットデータの送信が試行されます。データの送信に失敗すると、引き続きヒットデータがバッファーされます（この動作は、デバイスがオフラインの間継続します）。

### 設定メソッド

**setOfflineTrackingEnabled**:初期設定はfalseです。 測定ライブラリのオフライン追跡を有効または無効にします。

構文：

`void setOfflineTrackingEnabled(boolean Enabled);`

例："measure.setOfflineTrackingEnabled(true);

**setOfflineHitLimit**:初期設定は1000です。 キューに格納されるオフラインヒットの最大数。ヒットの上限を 5,000 以上に設定すると、アプリケーションのパフォーマンスに悪影響を及ぼすことがあります。

構文：

`void setOfflineHitLimit(int offlineHitLimit)`

例:

`measure.setOfflineHitLimit(2000);`

**getTrackingQueueSize**:オフラインキューに格納されたトラッキングコールの数を返します。

構文：

`int getTrackingQueueSize()`

例:

`int size = measure.getTrackingQueueSize();`

**clearTrackingQueue**:オフラインキューから保存されているすべてのトラッキングコールを削除します。

構文：

`void clearTrackingQueue()`

例:

`measure.clearTrackingQueue();`

**警告：キューを手動でクリアする場合は、慎重に実行してください。この操作を元に戻すことはできません。**


**setOnlineおよびsetOffline**:測定オブジェクトのオンライン状態またはオフライン状態を手動で設定します。 デバイスがオフラインであるかオンラインであるかは、ライブラリで自動的に検出されます。したがって、これらのメソッドは、測定を強制的にオフラインにする場合にのみ必要になります。setOnline は、手動でオフラインにした後にオンライン状態に戻す場合にのみ使用します。

測定がオフラインの場合：

* offlineTrackingEnabled が true の場合：ヒットは測定がオンラインになるまで保存されます。
* offlineTrackingEnabled が false の場合：ヒットは破棄されます。

構文：

```
void setOnline()
void setOffline()
```

例:

```
measure.setOffline();
measure.setOnline();
```

## オフライン追跡

AppMeasurement を使用すると、Android デバイスがオフラインの場合でもアプリケーションの使用状況を測定できます。

*注意：オフラインでの AppMeasurement を有効にするには、レポートスイートでタイムスタンプを有効にする必要があります。*

「オフライン追跡」を参照してください。

## Target

アドビでは、Android アプリケーション内でターゲティングされたコンテンツを提供するための機能を提供しています。

Test&amp;Targetから返されるコンテンツは、HTML、XML、プレーンテキストなどのテキストベースのコンテンツです。 ロードしたコンテンツを Android アプリケーションでどのように使用するかは開発者が自由に決められます。コンテンツは、HTML として表示することも、アプリケーションの動作を変更するために使うこともできます。このガイドでは、Test&amp;Target の各種クラスの簡単な使用例を示します。

要件

* JDK 5/6/7
* Android SDK for Platform 1.5 以降

ここで説明する例は、Eclipse をベースとしています。

**ライブラリの取得**

Developer Connection の「モバイルアプリケーションの測定と最適化￼」にアクセスして、Android ライブラリをダウンロードしてください。

ダウンロードファイルを解凍すると、次のソフトウェアコンポーネントが展開されます。

* admsAppLibrary.jar：Android デバイスとシミュレーターで使用するように設計されたライブラリ。Android 2.0 以降が必要です。
* Examples\TrackingHelper.java：トラッキングコードをアプリケーションロジックから分離するように設計されたオプションのクラス。

**プロジェクトへのライブラリの追加**

1. Eclipse IDE で、プロジェクト名を右クリックします。
1. Build Path（ビルドパス）／Add External Archives（外部アーカイブの追加）を選択します。
1. admsAppLibrary.jar を選択します。
1. 「Open（開く）」をクリックします。
1. プロジェクトを再度右クリックし、Build Path（ビルドパス）／Configure Build Path（ビルドパスを設定）を選択します。
1. 「Order and Export（順序とエクスポート）」タブをクリックします。
1. admsAppLibrary.jar が選択済みであることを確認します。

アプリケーションでは admsAppLibrary.jar ライブラリから `importcom.adobe.ADMS.*;` .*; を使ってクラスやインターフェイスをインポートすることができます。

**アプリの権限の追加**

AppMeasurement ライブラリでは、データの送信とオフラインのトラッキングコールの記録のために、次の権限が必要です。

* INTERNET
* ACCESS_NETWORK_STATE

これらの権限を追加するには、AndroidManifest.xml ファイル（アプリケーションのプロジェクトディレクトリ内）に次の行を追加します。

```
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

例

プロジェクトにライブラリを追加してアプリの権限を追加すると、MboxFactory と Mbox という 2 つの Test&amp;Target クラスを使用できるようになります。

次の例では、Test&amp;Target から単純な Android アプリケーション内部の WebView に HTML コンテンツをロードする方法を示します。この例では、関連する HTML オファーおよびキャンペーンが Test&amp;Target 管理ツールで既に作成済みであること、およびそのキャンペーンが承認済みであることを前提としています。

1. 実装の手順を実行したら、Application または Activity サブクラスの最初の部分で testandtarget パッケージをインポートします。

   `com.adobe.adms.testandtarget.*;`

2. 以下の番号の付いたコードに従って、mbox を作成します（コードの各行の説明についてはコメントを参照）。この手順を実行するには、Test&amp;Target 管理ツールでのキャンペーンの設定に使用したクライアントコードおよび mbox 名を把握しておく必要があります。

   ```
   public class AndroidDemoApplication extends Activity {
   private WebView _webView;
   public void onCreate(Bundle savedInstanceState) {
   super.onCreate(savedInstanceState);
   _webView = new WebView(this);
   setContentView(_webView);
   // 1. Create an instance of the MboxFactory class with your client code.
   MboxFactory factory = new MboxFactory("androiddemo16");
   // 2. Use the MboxFactory instance to create an Mbox.
   Mbox mbox = factory.create("DemoApp");
   // 3. Set the default content for the Mbox.
   mbox.setDefaultContent("<h1>DEFAULT CONTENT</h1>");
   /**
   * 4. Create a custom MboxContentConsumer to consume the content returned. The
   * CustomMboxContentConsumer class defined below simply displays the content
   * returned in a BrowserField as HTML.
   */
   CustomConsumer consumer = new CustomConsumer(_webView);
   mbox.addOnLoadConsumer(consumer);
   // 5. Load the Mbox.
   mbox.load();
   ...
   ```

3. MboxContentConsumer インターフェイスを実装するカスタムクラスを定義します。この抽象インターフェイスを実装するには、コンテンツを渡す「consume」メソッドだけを定義する必要があります。以下に定義した CustomConsumer クラスは、WebView の内容だけを表示します。

   ```
   class CustomConsumer implements MboxContentConsumer {
   private WebView _view;
   public CustomConsumer(WebView webview) {
   _view = webview;
   }
   public void consume(String content) {
   _view.loadData(content, "text/html", "utf-8");
   }
   }
   ```

4. プロジェクトを右クリックし、Run As（次を実行）／Android Application（Android アプリケーション）を選択して、アプリケーションのビルドとテストを実行します。Test&amp;Target キャンペーンを正しく設定し承認している場合は、Android デバイスエミュレーターにオファーが表示されます。

**ライフサイクル指標**

ライフサイクル指標が有効な場合、ライフサイクル指標は、各 mbox が読み込むパラメーターとして送信されます。

* （推奨）ライフサイクルイベントの追跡
* ライフサイクル指標

## Audience Management

アドビでは、シグナルを送信し、Audience Management から訪問者セグメントを取得する機能を提供しています。

### 要件

* JDK 5/6/7
* Android SDK for Platform 1.5 以降

ここで説明する例は、Eclipse をベースとしています。

### ライブラリの取得

Developer Connection の「モバイルアプリケーションの測定と最適化￼」にアクセスして、Android ライブラリをダウンロードしてください。

ダウンロードファイルを解凍すると、次のソフトウェアコンポーネントが展開されます。

* admsAppLibrary.jar：Android デバイスとシミュレーターで使用するように設計されたライブラリ。Android 2.0 以降が必要です。
* Examples\TrackingHelper.java：トラッキングコードをアプリケーションロジックから分離するように設計されたオプションのクラス。

### プロジェクトへのライブラリの追加

1. Eclipse IDE で、プロジェクト名を右クリックします。
1. Build Path（ビルドパス）／Add External Archives（外部アーカイブの追加）を選択します。
1. admsAppLibrary.jar を選択します。
1. 「Open（開く）」をクリックします。
1. プロジェクトを再度右クリックし、Build Path（ビルドパス）／Configure Build Path（ビルドパスを設定）を選択します。
1. 「Order and Export（順序とエクスポート）」タブをクリックします。
1. admsAppLibrary.jar が選択済みであることを確認します。

アプリケーションでは admsAppLibrary.jar ライブラリから `importcom.adobe.ADMS.*;` .*; を使ってクラスやインターフェイスをインポートすることができます。

### アプリの権限の追加

AppMeasurement ライブラリでは、データの送信とオフラインのトラッキングコールの記録のために、次の権限が必要です。
* INTERNET
* ACCESS_NETWORK_STATE

これらの権限を追加するには、AndroidManifest.xml ファイル（アプリケーションのプロジェクトディレクトリ内）に次の行を追加します。

```
<uses-permission android:name="android.permission.INTERNET" />
<uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
```

### コードサンプル

プロジェクトにライブラリを追加したら、ADMS_AudienceManager クラスを使用できます。To import the audience manager package add: `import com.adobe.adms.audiencemanager;`

1. Audience Management を設定します。

   `ADMS_AudienceManager.ConfigureAudienceManager("mycompany.demdex.net", this);`

   mycompany.demdex.net をエンドポイントで置き換えます。Audience Management は、アプリケーションのどの時点でも設定できます。


2. オプションで、dpid および dpuuid を設定します。

   `ADMS_AudienceManager.SetDpidAndDpuuid("284", "abc123");`

3. 特性ディクショナリを作成し、シグナルでディクショナリを送信します。

```
HashMap<String, Object> data = new HashMap<String, Object>();
data.put("trait", "b");
ADMS_AudienceManager.SubmitSignal(data, new
ADMS_AudienceManager.AudienceManagerCallback<HashMap>() {
@Override
public void call(HashMap visitorProfile) {
// do things with visitorProfile
}
});
```

訪問者プロファイルディクショナリは、content パラメーターとしてコールバックで返されます。

### ライフサイクル指標

ライフサイクル指標が有効で、Audience Management が application:didFinishLaunchingWithOptions: に設定されている場合、設定が完了した後、ライフサイクル指標を含むシグナルが送信されます。

* （推奨）ライフサイクルイベントの追跡
* ライフサイクル指標

### ADMS_AudienceManager リファレンス

**メソッド**

**ConfigureAudienceManager**:Audience Managementエンドポイントを設定します。

構文：

`public static void ConfigureAudienceManager(String server, Context context);`

例：

`ADMS_AudienceManager.ConfigureAudienceManager("mycompany.demdex.net", this);`

**GetDebugLogging**:Audience Managerメソッドがコンソールにデバッグログを提供するかどうかを示すブール値を返します。

構文：

`public static boolean GetDebugLogging();`

**GetDpid**:dpidを返します。

構文：

`public static String GetDpid();`

**GetDpuuid**:dpuuidを返します。

構文：

`public static String GetDpuuid();`

**GetVisitorProfile**:このメソッドは、最新の訪問者プロファイルを取得するシグナルを送信した後、いつでも呼び出すことができます。

訪問者プロファイルには、stuff オブジェクトで返されたすべてのキーと値のペアが含まれています。

構文：

`public static HashMap GetVisitorProfile();`

**SetDebugLogging**:コンソールのデバッグログを有効または無効にします。

構文：

`public static void SetDebugLogging(boolean logging);`

**SetDpidAndDpuuid**:newDpidとnewDpuuidが設定されている場合、各シグナルと共に送信されます。

構文：

`public static void SetDpidAndDpuuid(String newDpid, String newDpuuid);`

**SubmitSignal**:特性のディクショナリに送信し、更新された訪問者プロファイルをコールバックで受け取ります。

JSON 応答からの uuid が内部的に格納され、その後のすべてのシグナルで使用されます。また、ピクセルリクエストが、dests オブジェクトで見つかった各 URL に送信されます。

構文：

```
public static void SubmitSignal(HashMap<String, Object> data,
AudienceManagerCallback<HashMap> callback);
```

### インターフェイス

**メソッド**


**AudienceManagerCallback**

構文：

```
public interface AudienceManagerCallback<T> {
AudienceManagerCallback
public void call(T item);
}
```

SubmitSignal 呼び出しからのコールバックで使用されるオブジェクト用のインターフェイス。


## PhoneGap プラグイン

このプラグインを使用すると、PhoneGap プロジェクトから Android AppMeasurement コールを送信できます。

PhoneGap プロジェクトの作成については、PhoneGap での Android 使用の手引きを参照してください。

プラグインをダウンロードするには、SiteCatalyst 用の PhoneGap iOS プラグインや Android プラグインを参照してください。

### プラグインの取り込み

1. src フォルダー内のパッケージに、ADMS_plugin.java をコピーします。
2. PhoneGap プロジェクトの assets/www/js フォルダーに、ADMS_Helper.js をコピーします。
3. In the res/xml folder, open config.xml file and register an new plugin by creating a new child node under plugins: `<plugin name="ADMS_Plugin" value="[YOUR_PACKAGE_NAME].ADMS_plugin" />`

For example, if you package is named com.example.phonegaptest, then your plugin node would be the following: `<plugin name="ADMS_Plugin" value="com.example.phonegaptest.ADMS_plugin" />`

### AppMeasurement ライブラリの取り込み

AppMeasurement ライブラリをダウンロードするには、ライブラリの取得を参照してください。

1. PhoneGap プロジェクトの libs フォルダーに admsAppLibrary.jar をコピーします。
2. 「libs」を右クリックし、Build Path（ビルドパス）／Configure Build Path（ビルドパスを設定）を選択して、admsAppLibrary.jar がビルドパス内にあることを確認します。
3. 「Libraries」タブのリストにJARファイルがない場合は、「Add JARs」をクリックし、libsフォルダーからadmsAppLibrary.jarを選択します。


### ライフサイクル指標の自動追跡

トラッキングライフサイクル指標の追跡では、PhoneGap 以外の設定が必要になります。ライフサイクルの自動追跡を有効にするには、開発者クイックスタートの実装の手順を実行してください。

### プラグインの使用

追跡に使用する html ファイルに、以下を追加します。

`<script type="text/javascript" src="js/ADMS_Helper.js"></script>`

これで、測定コールを実行する準備ができました。PhoneGap プラグインのメソッドを参照してください。

### トラブルシューティング

**構文は正しいのですが、プラグイン内のコードに処理が到達しないのはなぜですか。**

Check your output console for the following error: `java.lang.ClassNotFoundException: ADMS_plugin`

このエラーが発生する場合は、「プラグインを含める」の手順3を実行したことを確認してください。

## PhoneGap プラグインのメソッド

これらのメソッドを使用する html ファイルに、以下を追加します。

`<script type="text/javascript" src="js/ADMS_Helper.js"></script>`

**設定メソッド**


**configureMeasurementWithReportSuiteIDsTrackingServer**:このメソッドは、アプリケーション測定を開始するために必要な2つのパラメーターを設定するために使用します。 サーバーコールを送信する前に、このメソッドを使用して測定オブジェクトの reportSuiteIDs および trackingServer の値を設定する必要があります。

構文：

`void configureMeasurementWithReportSuiteIDsTrackingServer(stringreportSuiteIDs, string trackingServer);`

例：

`ADMS.configureMeasurementWithReportSuiteIDsTrackingServer("testRSID","10.20.40.199:5050");`

**setOnlineおよびsetOffline**:測定オブジェクトのオンライン状態またはオフライン状態を手動で設定します。 デバイスがオフラインであるかオンラインであるかは、ライブラリで自動的に検出されます。したがって、これらのメソッドは、測定を強制的にオフラインにする場合にのみ必要になります。setOnline は、手動でオフラインにした後にオンライン状態に戻す場合にのみ使用します。

測定がオフラインの場合：

* offlineTrackingEnabled が true の場合：ヒットは測定がオンラインになるまで保存されます。
* offlineTrackingEnabled が false の場合：ヒットは破棄されます。

構文：

```
void setOnline();
void setOffline();
```

例：

```
ADMS.setOnline();
ADMS.setOffline();
```

**setDebugLogging**:デバッグ情報を表示する設定を、有効(True)または無効(False)にします。 デフォルトでは、この変数は false です。

この変数は、変数のオーバーライドを使用して上書きできません。

構文：

`void setDebugLogging(bool debugLogging);`

例：

`ADMS.setDebugLogging(true);`

### イベントおよび状態の追跡メソッド


**trackAppState**:アプリケーション内のアプリケーション状態（ページなど）を追跡する場合に推奨される方法です。 appState に指定した値は、サーバーコールのページ名変数として表示されます。appState 文字列は、次回のコールまで持ち越されないので、呼び出すたびに指定する必要があります。

構文：

`void trackAppState(string stateName);`

例：

`ADMS.trackAppState("login page");`

**trackAppStateWithContextData**:アプリケーション内のアプリケーション状態（ページなど）を追跡する場合に推奨される方法です。 appState に指定した値は、サーバーコールのページ名変数として表示されます。appState 文字列は、次回のコールまで持ち越されないので、呼び出すたびに指定する必要があります。

このコールの 2 つめの引数で指定されるコンテキストデータは、persistentContextData のすべての値に追加され、コールと共に送信されます。persistentContextData に設定した値のみが次回のコールまで維持されます。

構文：

`void trackAppStateWithContextData(string stateName, JSON cData);`

cData：コンテキストデータで送信されるキーと値のペアを持つ JSON オブジェクト。

例：

```
trackAppStateWithContextData("login page",
{"user":"john","remember":"true"});
```

**trackEvents**:アプリケーション内のイベントを追跡する場合は、この方法をお勧めします。 trackEventsはtrackAppStateに似ていますが、ページ名ではなくイベントを送信します。 イベントは、カンマで区切られたtrackEvents文字列として提供されます。 events 文字列は、次回のコールまで持ち越されないので、呼び出すたびに指定する必要があります。

このメソッドは、内部でtrackLinkURLを呼び出します。この際、linkURLはnullに、linkTypeは"o"に設定され、linkNameはアプリケーションIDを使用して設定されます。

つまり、linkTrackVars と linkTrackEvents が、`trackEvents` へのコールに適用されます。

構文：

`void trackEvents(string eventNames);`

例：

`ADMS.trackEvents("login,event2");`

**trackLink メソッドを使用するときの注意事項**

`trackEvents` では、内部で trackLinkURL が呼び出されます。この際、linkURL は null に、linkType は "o" に設定され、linkName はアプリケーション ID を使用して設定されます。この処理は、ページビュー（状態ビュー）のカウントがイベントを追跡するたびに増加するのを防ぐために行われます。

trackLinkURL を直接呼び出して、linkTrackVars および linkTrackEvents の値を設定すると、これらの変数およびイベントの制約が TrackEvents に適用されます。つまり、これらのリストに定義されている変数およびイベントのみが、TrackEvents によって送信されます。このような制約を trackEvents に適用したくない場合は、linkTrackVars および linkTrackEvents を null に設定してください。

**trackEventsWithContextData**:アプリケーション内のイベントを追跡する場合は、この方法をお勧めします。 trackEventsはtrackAppStateに似ていますが、ページ名ではなくイベントを送信します。 イベントはコンマ区切りの文字列で指定します。events 文字列は、次回のコールまで持ち越されないので、呼び出すたびに指定する必要があります。

このメソッドでは、内部で trackLinkURL が呼び出されます。この際、linkURL は null に、linkType は "o" に設定され、linkName はアプリケーション ID を使用して設定されます。

つまり、linkTrackVars と linkTrackEvents が、trackEvents へのコールに適用されます。

このコールの 2 つめの引数で指定されるコンテキストデータは、persistentContextData のすべての値に追加され、コールと共に送信されます。persistentContextData に設定した値のみが次回のコールまで維持されます。

構文：

`void trackEventsWithContextData(string eventNames, JSON cData);`

cData：コンテキストデータで送信されるキーと値のペアを持つ JSON オブジェクト。

例：

`ADMS.trackEventsWithContextData("login,event2",
{"user":"john","remember":"true"});`

**trackLink メソッドを使用するときの注意事項**

trackEvents では、内部で trackLinkURL が呼び出されます。この際、linkURL は null に、linkType は "o" に設定され、linkName はアプリケーション ID を使用して設定されます。この処理は、ページビュー（状態ビュー）のカウントがイベントを追跡するたびに増加するのを防ぐために行われます。

trackLinkURL を直接呼び出して、linkTrackVars および linkTrackEvents の値を設定すると、これらの変数およびイベントの制約が TrackEvents に適用されます。つまり、これらのリストに定義されている変数およびイベントのみが、TrackEvents によって送信されます。このような制約を trackEvents に適用したくない場合は、linkTrackVars および linkTrackEvents を null に設定してください。

**高度な追跡メソッド（track と trackLink）)**

以下のメソッドには、追加の追跡オプションが用意されています。これらのオプションによって、prop や eVar などの SiteCatalyst 変数を直接設定できます。これらのオプションは、既存の SiteCatalyst の実装を使用するお客様、または他の SiteCatalyst の実装を詳細に理解しているお客様が使用してください。

`track` および `trackLink` は主要な測定メソッドであり、複数のプラットフォームにおける Adobe Measurement Library のすべてのバージョンに実装されます。モバイルアプリケーションの追跡を行うほとんどの状況で、trackAppState メソッドおよび trackEvents メソッドを使用するほうが、track および trackLink を直接呼び出すよりも簡単です。

ページビュー追跡（track）およびリンク追跡（trackLink）では、値（null、空、ゼロ以外の値）を持つすべての永続的な変数が送信されます。track または trackLink を呼び出す前に、必要に応じてすべての変数をリセットするか、空にする必要があります。

**メソッド**

**track**:標準のページビューと、測定オブジェクトに設定された追加の変数を収集サーバーに送信します。

構文：

`void track();`

例：

`ADMS.track();`

**trackWithContextData**:標準のページビューと、測定オブジェクトに設定された追加の変数を収集サーバーに送信します。

trackWithContextDataを呼び出すたびに、測定オブジェクトに定義されているすべての永続的なデータ（clearVarsの説明に記載されているもの）と、そのコールのみに指定したすべてのcontextDataが送信されます。

構文：

`void trackWithContextData(JSON cData);`

cData：コンテキストデータで送信されるキーと値のペアを持つ JSON オブジェクト。

例：

`ADMS.trackWithContextData({"key1":"value1","key2":"value2"});`


**trackWith ContextDataAndVariables**:標準のページビューと、測定オブジェクトに設定された追加の変数を収集サーバーに送信します。

trackWithContextDataAndVariablesを呼び出すたびに、測定オブジェクトに定義されたすべての永続的なデータ（clearVarsの説明に記載されているもの）と、そのコールのみに指定したすべてのcontextDataと変数が送信されます。 値がセットされた後者は、対応する永続的な変数に設定された値を上書きします。

構文：

`void trackWithContextDataAndVariables(JSON cData, JSON vars);`

cData：コンテキストデータで送信されるキーと値のペアを持つ JSON オブジェクト。

例：

```
ADMS.trackWithContextDataAndVariables({"key1":"value1","key2":"value2"},
{"eVar1":"newValue","prop3":"newValue"});
```

**trackLinkURLWithLinkTypeName**:カスタム、ダウンロード、または離脱リンクのデータを、値を持つトラック設定変数と共にアドビのデータ収集サーバーに送信します。

ページビューをカウントアップすべきではないアクティビティを追跡する場合に、trackLink を使用します。

trackLinkURLWithLinkTypeNameContextDataVariablesを呼び出すたびに、測定オブジェクトに定義されたすべての永続的なデータ（clearVarsの説明に記載されているもの）と、そのコールのみに指定したすべてのcontextDataが送信されます。

構文：

```
void trackLinkURLWithLinkTypeNameContextDataVariables(string`
linkUrl, string linkType, string linkName, JSON cData, JSON vars);
```

cData：コンテキストデータで送信されるキーと値のペアを持つ JSON オブジェクト。

例：

```
ADMS.trackLinkURLWithLinkTypeNameContextDataVariables("theLink",
"o", "logout", {"key1":"value1"}, {"eVar1":"newValue"});
```

### AppMeasurement 変数の設定と取得

**メソッド**

**setEvarToValue**:指定したeVarに指定した値を設定します。 この eVar は次回のトラッキングコールと共に送信されます。

構文：

`void setEvarToValue(int evar, string value);`

例：

`ADMS.setEvarToValue(1, "newValue");`

**setPropToValue**:指定したpropに指定した値を設定します。 この prop は次回のトラッキングコールと共に送信されます。

構文：

void setPropToValue(int prop, string value);

例：

`ADMS.setPropToValue(1, "newValue");`

**setHierToValue**:指定したhier変数に指定した値を設定します。 この変数は次回のトラッキングコールと共に送信されます。

構文：

`void setHierToValue(int hier, string value);`

例：

`ADMS.setHierToValue(1, "newValue");`

**setListVarToValue**:指定したlistvarに指定した値を設定します。 このリスト変数は次回のトラッキングコールと共に送信されます。

構文：

`void setListVarToValue(int list, string value);`

例：

`ADMS.setListVarToValue(1, "newValue");`

**getEvar**:指定した変数を取得します。

構文：

`void getEvar(int evar, function success, function fail);`

例：

```
ADMS.getEvar(1, function (value) { myTempEvar1 = value; }, function ()
{ myTempEvar1 = null; });
```

**getProp**:指定した変数を取得します。

構文：

`void getProp(int prop, function success, function fail);`

例：

```
ADMS.getProp(1, function (value) { myTempProp1 = value; }, function ()
{ myTempProp1 = null; });
```

**getHier**:指定した変数を取得します。

構文：

`void getHier(int hier, function success, function fail);`

例：

```
ADMS.getHier(1, function (value) { myTempHier1 = value; }, function ()
{ myTempHier1 = null; });
```

**getListVar**:指定した変数を取得します。

構文：

`void getListVar(int list, function success, function fail);`

例：

```
ADMS.getListVar(1, function (value) { myTempListVar1 = value; }, function
() { myTempListVar1 = null; });
```

**clearVars**:オブジェクト上の次の変数から値を削除します。

```
props
eVars
heirs
listVars
events
PersistentContextData
purchaseID
transactionID
appState
channel
appSection
campaign
products
geoZip
geoState
linkTrackVars
linkTrackEvents
```

構文：

`void clearVars();`

例：

`ADMS.clearVars();`

**trackingQueueSize**:オフラインキューに格納されているトラッキングコールの数を取得または設定します。

構文：

`void trackingQueueSize(function success, function fail);`

例：

`ADMS.trackingQueueSize(function (value) { myQueueSize = value; }, function () { myQueueSize = 0; });`

**clearTrackingQueue**:オフラインキューから保存されているすべてのトラッキングコールを削除します。 警告：キューを手動でクリアする場合は、慎重に実行してください。この操作を元に戻すことはできません。

構文：

`void clearTrackingQueue();`

例：

`ADMS.clearTrackingQueue();`

### 設定変数の設定と取得

**メソッド**

**getVersion**:ライブラリのバージョンを取得します。

構文：

`void getVersion(function success, function fail);`

例：

```
ADMS.getVersion(function (value) { versionNum = value; }, function ()
{ versionNum = 1.0; });
```

**setReportSuiteIDs**:（必須）追跡する1つまたは複数のレポートスイート（マルチスイートタギング）。 複数のレポートスイートを追跡するには、各レポートスイート名をコンマで区切ったリストを渡します。

この変数は 1 回のコールでオーバーライドすることができません。永続的な値を変更する必要があります。

構文:
`void setReportSuiteIDs(string reportSuiteIDs);`

例：

`ADMS.setReportSuiteIDs("rsid1, rsid2");`

**setTrackingServer**:（必須）収集サーバーを識別します。

この変数には、コードマネージャーで生成された値を指定する必要があります。

SSL が有効な場合は、安全な追跡でも同じ値が使用されます。

この変数は 1 回のコールでオーバーライドすることができません。永続的な値を変更する必要があります。

構文：

`void setTrackingServer(string trackingServer);`

例：

`ADMS.setTrackingServer("10.23.52.191:5923");`

**setDataCenter**:

構文：

`void setDataCenter(string dataCenter);`

例：

`ADMS.setDataCenter("myDataCenter");`

**setVisitorID**:初期設定はCFUUIDです。

各訪問者の一意識別子。カスタムの visitorID を設定しない場合は、初期起動時に一意の visitorID が（Apple の CFUUID を使用して）生成され、ユーザーのデフォルトのキーに格納されます。このキーはそれ以降、AppMeasurement と PhoneGap によって使用されます。また、このキーはアプリケーションの標準的なバックアッププロセスでも保存、復元されます。

構文：

`void setVisitorID(string visitorId);`

例：

`ADMS.setVisitorID("myVisitorId");`

**setCharSet**:初期設定はUTF-8です。

構文：

`void setCharSet(string charSet);`

例：

`ADMS.setCharSet("UTF-8");`

**setCurrencyCode**:デフォルトはなし（レポートスイート用に定義された値が使用されます）。

iOS アプリケーション内で追跡する購入イベントや通貨イベントの通貨コード。

構文：

`void setCurrencyCode(string currencyCode);`

例：

`ADMS.setCurrencyCode("USD");`


**setSSLEnabled**:デフォルトはfalseです。

SSL（HTTPS）を介した測定データの送信設定を有効（true）または無効（false）にします。この変数は 1 回のコールでオーバーライドすることができません。永続的な値を変更する必要があります。

構文：

`void setSSLEnabled(bool sslEnabled);`

例：

`ADMS.setSSLEnabled(false);`

### 永続的なトラッキング変数の設定と取得

**メソッド**

**setPurchaseID**:

構文：

`void setPurchaseID(string purchaseId);`

例：

`ADMS.setPurchaseID("purchase1");`

**setTransactionID**:

構文：

`void setTransactionID(string transactionId);`

例：

`ADMS.setTransactionID("transaction1");`

**setAppState**:

構文：

`void setAppState(string stateName);`

例：

`ADMS.setAppState("myAppState");`

**setChannel**:

構文：

`void setChannel(string channel);`

例：

`ADMS.setChannel("myChannel");`

**setAppSection**:

構文：

`void setAppSection(string appSection);`

例：

`DMS.setAppSection("myAppSection");`

**setCampaign**:

構文：

`void setCampaign(string campaign);`

例：

`ADMS.setCampaign("myCampaign");`

**setProducts**:

構文：

`void setProducts(string products);`

例：

`ADMS.setProducts("myProduct1,myProduct2");`

**setEvents**:

構文：

`void setEvents(string events);`

例：

`ADMS.setEvents("event1, event2");`

**setGeoState**

構文：

`void setGeoState(string state);`

例：

`ADMS.setGeoState("FL");`

**setGeoZip**:

構文：

`void setGeoZip(string zip);`

例：

`ADMS.setGeoZip("39984");`

**setPersistentContextData**:コンテキストデータは、データを収集するための推奨される方法です。 コンテキストデータを送信するには、JSON オブジェクトを作成し、送信する値に対してキーと値のペアを割り当てます。

構文：

`void setPersistentContextData(JSON cData);`

例：

`ADMS.setPersistentContextData({"key1":"value1"});`

**persistentContextData**:

構文：

`void persistentContextData(function success, function fail);`

例：

```
ADMS.persistentContextData(function(value) { alert(value); },
function(error) { alert(error); });
```

**setLinkTrackVars**:変数名のコンマ区切りリスト。このリストは、リンクトラッキングを制限する変数の現在のセットです。

linkTrackVars を定義していない場合、PhoneGap プラグインでは trackLink コールと共に定義済みのすべての変数が送信されます。

構文：

`void setLinkTrackVars(string linkTrackVars);`

例：

`ADMS.setLinkTrackVars("eVar1,eVar2");`


**setLinkTrackEvents**:イベントのコンマ区切りのリスト。現在のイベントセットはリンクの追跡が制限されます。 linkTrackEvents を定義していない場合、PhoneGap プラグインでは trackLink コールと共にすべてのイベントが送信されます。

構文：

`void setLinkTrackEvents(string linkTrackEvents);`

例：

`ADMS.setLinkTrackEvents("event1,loginEvent");`


**setLightTrackVars**:変数のコンマ区切りリスト。現在の変数セットはライトトラッキングコールが制限されます。 Light Server Call で送信されるこれらの変数は、ClientCare で設定します。

構文：

`void setLightTrackVars(string lightTrackVars);`

例：

`ADMS.setLightTrackVars("prop1,hier3");`

### オフライン追跡

**メソッド**

**setOfflineTrackingEnabled**:

構文：

`void setOfflineTrackingEnabled(bool offlineTrackingEnabled);`

例：

`ADMS.setOfflineTrackingEnabled(true);`

**setOfflineHitLimit**:

構文：

`void setOfflineHitLimit(int offlineHitLimit);`

例：

`ADMS.setOfflineHitLimit(3000);`

## Android バージョン 2.x から 3.x への移行ガイド

* AppMeasurement が ADMS_Measurement と改称されました。このクラスを参照している場所を検索し、名前を ADMS_Measurement に更新してください。
* getInstance が sharedInstance と改称されました。getInstance を呼び出している場所を検索し、sharedInstance に置き換えてください。
* churn measurement（チャーン測定）（getChurnInstance）へのすべてのコールを削除してください。これらのコールは自動追跡によって処理され、コンテキストデータを使用して変数が挿入されるようになりました。
* Timestamp は廃止されました。タイムスタンプはライブラリによって自動的に処理されます。

次のメソッドの構文が変更されました。すべてのプロパティおよびメソッドに関する更新後の例は、 設定変数とメソッドを参照してください。


### レポートスイート

**以前のバージョン（2.1.x）**

`account`

**新しいバージョン（3.x）**

`reportSuiteIDs`

### Track

**以前のバージョン（2.1.x）**


`String track()`

`String track(Hashtable variableOverrides)`

**新しいバージョン（3.x）**

使用しない値には null を渡します。

```
void track()
void track(Hashtable<String, Object>
contextData)
void track(Hashtable<String, Object>
contextData, Hashtable<String, Object>
variables)
```

### リンクを追跡

**以前のバージョン（2.1.x）**

```
String trackLink(String linkURL, String
linkType, String linkName)
```

```
String trackLink(String linkURL, String
linkType, String linkName,
Hashtable variableOverrides)
```

**新しいバージョン（3.x）**

以前のバージョンの 2 つのコールは、1 つのコールに置き換えられました。使用しない値には null を渡します。

```
void trackLink(String linkURL, String linkType,
String linkName,
Hashtable<String, Object> contextData,
Hashtable<String, Object> variables)
```

### オフライン追跡メソッド

**以前のバージョン（2.1.x）**

`void forceOffline();`


`void forceOnline();`

**新しいバージョン（3.x）**

`void setOnline();`

`void setOffline();`


### 名前が変更された変数

次に、バージョン 2.x の変数と、それに対応する 3.x での値を示します。バージョン 3.x ではモバイルに重点を置いたライブラリにして導入を簡素化するために、いくつかの変数が廃止されています。


*注意：バージョン 3.x では、パブリック変数の代わりに getter と setter が使用されます。コードで変数を直接設定している場合は、get メソッドと set メソッドに更新してください。*

```
timestamp; //Removed
trackOffline; //void setOfflineTrackingEnabled(boolean Enabled)
offlineLimit; //void setOfflineHitLimit(int offlineHitLimit)
account; //reportSuiteIDs
linkURL; //Removed (sent with linkTrackURL)
linkName; //Removed (sent with linkTrackURL)
linkType; //Removed (sent with linkTrackURL)
linkTrackVars; //void setLinkTrackVars(String Vars) //comma-delimited list
linkTrackEvents; //void setLinkTrackEvents(String Events) //comma-delimited list
dc; //Removed
trackingServer; //void setTrackingServer(String trackingServer)
trackingServerSecure; //Removed, trackingServer value is used for secure server if ssl=YES
userAgent; //Removed
dynamicVariablePrefix; //Removed
visitorID; //void setVisitorID(String ID)
charSet; //void setCharSet(String charSet)
visitorNamespace; //Removed
pageName; //void setAppState(String State)
pageURL; //Removed
referrer; //Removed
currencyCode; //void setCurrencyCode(String currencyCode)
purchaseID; //void setPurchaseID(String ID)
channel; //void setChannel(String Channel)
server; //void setAppSection(String Section)
pageType; //Removed
transactionID; //void setTransactionID(String ID)
campaign; //void setCampaign(String Campaign)
state; //void setGeoState(String GeoState)
zip; //void setGeoZip(String GeoZip)
events; //void setEvents(String Event) //comma-delimited list
products; //void setProducts(String Products)
list1-list3; //setListVar(int listNum, String listValue);
hier1-heir5; //setHier(int hierNum, String hierValue);
prop1-prop75; //setProp(int propNum, String propValue);
eVar1-eVar75; //setEvar(int evarNum, String evarValue);
ssl; //void setSSL(boolean ssl)
linkLeaveQueryString; //Removed
debugTracking; //debugLogging
usePlugins; //Removed
useBestPractices; //Removed - handled by Lifecycle AutoTracking
contextData; //persistentContextData
```

## Bloodhound を使用したモバイルアプリケーションのテスト

Bloodhound ツールを使用すると、ローカルコンピューターにサーバーコールを送信して、モバイルアプリケーションをテストすることができます。

*重要：Adobe Bloodhound は、2017 年 4 月 30 日をもって廃止されました。2017 年 5 月 1 日以降、追加の機能強化や追加のエンジニアリングまたは Adobe Expert Care のサポートは提供されません。*

アプリケーションの開発中に Bloodhound を使用すると、サーバーコールをローカルで表示できます。また、必要に応じてアドビの収集サーバーにデータを転送することもできます。

Bloodhound は、Mac OS と Windows で利用できます。

### 要件

* Snow Leopard（10.6）以降が実行されている Intel ベースの Mac OS コンピューター、または Windows PC。
* ご使用のモバイルデバイスまたはシミュレーターへのネットワーク接続。

### ダウンロード

Developer Connection の Bloodhound - アプリケーション測定 QA ツールを参照してください。

### インストール

* Mac OS：ダウンロードした dmg を開き、Applications フォルダーに Bloodhound をドラッグします。
* Windows：ダウンロードしたインストールファイルを実行します。

### Bloodhound の使用

ツールを起動しても、「開始」ボタンをクリックするまでサーバーは無効のままです。アプリケーションからサーバーコールを収集する準備ができたら、「開始」ボタンをクリックします。

必要に応じて、サーバーを起動する前に、カスタムポート番号（1024 よりも大きい番号）を指定できます。ポート番号を指定しなかった場合は、開いているポートが自動的に選択されます。

次の節でも説明しますが、サーバーを実行したら、アプリケーションまたはデバイスからツールにデータを送信するように設定する必要があります。

### Bloodhound にヒットを送信するようにデバイスを設定する

デバイスのプロキシ設定を変更して、ツールに http リクエストを送信できます。ツールに送信したリクエストは、必要に応じてアドビのデータ収集サーバーに転送できます。

デバイスでプロキシがサポートされていない場合は、Bloodhound に直接ヒットを送ってテストできます。

*注意：Bloodhound では、SSL トラッキングがサポートされていません。Bloodhound を使用してテストするときは、AppMeasurement ライブラリで SSL を無効にする必要があります。*

#### iOS デバイス

iOS デバイスは、Bloodhound をホストするコンピューターと同じネットワーク上に存在する必要があります。

1. 設定／Wi-Fi に移動します。
1. 現在の Wi-Fi ネットワークの右にある青い矢印をクリックします。
1. 「HTTP プロキシ」設定までスクロールします。
1. 「自動」を選択します。
1. 「URL」フィールドにプロキシ URL とポート（Bloodhound の UI）を入力します。

#### その他のデバイス

デバイスでプロキシの自動設定がサポートされている場合は、プロキシ URL（Bloodhound の UI）をプロキシ自動設定（PAC）URL として使用します。Android でのプロキシサポートは、Android のバージョンによって異なります。Android 用のプロキシ設定ツールを使用すると、プロキシを簡単に設定できます。

### ヒットを直接送信する

プロキシをサポートしていないデバイス（iOS シミュレーター、Android の以前のバージョンなど）では、Bloodhound をトラッキングサーバーとして指定して、生成されるヒットを収集できます。これを行うには、トラッキングサーバーを<Bloodhound IP>:<BloodhoundPort>".

次に例を示します。

```
//iOS
[measure configureMeasurementWithReportSuiteIDs:@"my_rsid" trackingServer:@"10.10.2.2:5000"];
measure.ssl = NO;
```

```
//Android
measure.configureMeasurement("my_rsid", "10.10.2.2:5000");
measure.ssl = false;
```

```
//WinRT for Windows 8, Windows Phone 8
measure.ConfigureMeasurement("my_rsid", "10.10.2.2:5000");
measure.ssl = false;
```

### トラブルシューティング／一般的な問題点

* Bloodhound は、非 SSL トラッキングでのみ機能します。上記の方法とは関係なく、SSL を介して送信されたトラッキングヒットは収集されません。

## Android ウィジェット

Android ウィジェットは、アプリと同じメソッドを使用して追跡できます。ウィジェットは、アプリケーションコンテキストをアプリと共有するので、ヒットの順番および訪問者 ID は保持されます。

以下のガイドラインは、Android ウィジェットを追跡するのに役立ちます。

* ウィジェット自体に、ライフサイクル指標（startActivity／stopActivity）呼び出しを実装しない。
* ウィジェットがいつホーム画面に追加されたかを追跡するには、trackState または trackEvent 呼び出しをウィジェットの onEnabled メソッドに追加します。
* アプリがいつウィジェットから起動されたかを追跡するには、アプリケーションを起動するインテントを作成する前に、trackState または trackEvent 呼び出しを追加します。
* アクションのコンテキストの追跡に関心がある場合、それぞれ個別にセグメント化するオプションを提供する ContextData 変数を定義できます（例：AppExperienceType="widget" か "app" か）。
