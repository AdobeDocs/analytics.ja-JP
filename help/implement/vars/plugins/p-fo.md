---
title: p_fo（Page First Only）
description: 特定のルーチンが 1 ページにつき 1 回だけ実行されるようにします。
feature: Appmeasurement Implementation
exl-id: e82d77f9-2ea9-4b1b-b645-b12879c344ec
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '708'
ht-degree: 77%

---

# アドビプラグイン：p_fo（Page First Only）

{{plug-in}}

`p_fo` プラグインは、特定の JavaScript オブジェクトが存在するかどうかを確認するユーティリティです。オブジェクトが存在しない場合は、オブジェクトを作成して `true` を返します。JavaScript オブジェクトが既にページ上に存在する場合は、`false` を返します。このプラグインは、ページ上でコードを 1 回だけ実行する場合に便利です。その他のプラグインの一部は、このコードを使用して動作します。ページ上でのコードの実行回数を気にしない場合や、依存プラグインを使用しない場合は、このプラグインは不要です。

## Web SDK拡張機能を使用したプラグインのインストール

Adobeには、web SDKで最も一般的に使用されるプラグインを使用できる拡張機能が用意されています。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 左側の **[!UICONTROL タグ]** をクリックしてから、目的のタグプロパティをクリックします。
1. 左側の **[!UICONTROL 拡張機能]** をクリックしてから、「**[!UICONTROL カタログ]**」タブをクリックします
1. **[!UICONTROL Common Web SDK Plugins]** 拡張機能を見つけてインストールします。
1. 左側の **[!UICONTROL データ要素]** をクリックしてから、目的のデータ要素をクリックします。
1. 次の設定で、目的のデータ要素名を設定します。
   * 拡張機能：Common Web SDK Plugins
   * データ要素：`p_fo`
1. 変更を保存してデータ要素に公開します。

## Web SDKを手動で実装するプラグインのインストール

このプラグインは、web SDKの手動実装内での使用はまだサポートされていません。

## Adobe Analytics拡張機能を使用してプラグインをインストールします

Adobeには、Adobe Analyticsで最も一般的に使用されるプラグインを使用できる拡張機能があります。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のタグプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、「[!UICONTROL カタログ]」ボタンをクリックします。
1. [!UICONTROL Common Analytics Plugins] 拡張機能をインストールして公開します。
1. まだ「Initialize Plug-ins」というルールを作成していない場合は、次の設定を使用してルールを作成します。
   * Condition：なし
   * Events：Core – 読み込まれたライブラリ（ページ上部）
1. 次の設定を使用して、上記のルールにアクションを追加します。
   * Extension：Common Analytics Plugins
   * Action Type：Initialize p_fo
1. ルールに対する変更を保存して発行します。

## カスタムコードエディターを使用したプラグインのインストール

Common Analytics Plugins プラグイン拡張機能を使用しない場合は、カスタムコードエディターを使用できます。

1. Adobe ID 資格情報を使用して、[Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) にログインします。
1. 目的のプロパティをクリックします。
1. 「[!UICONTROL 拡張機能]」タブに移動し、Adobe Analytics 拡張機能の下にある「**[!UICONTROL 設定]**」ボタンをクリックします。
1. 「[!UICONTROL カスタムコードを使用してトラッキングを設定]」アコーディオンを展開すると、「[!UICONTROL エディターを開く]」ボタンが表示されます。
1. カスタムコードエディターを開き、下に示すプラグインコードを編集ウィンドウに貼り付けます。
1. 変更を保存し、Analytics 拡張機能に公開します。

## AppMeasurement を使用したプラグインのインストール

Analytics トラッキングオブジェクトをインスタンス化（[`s_gi`](../functions/s-gi.md) を使用）した後、AppMeasurement ファイルの任意の場所に次のコードをコピーして貼り付けます。実装時のコードのコメントとバージョン番号を記録しておくと、アドビが潜在的な問題のトラブルシューティングを行う際に役立ちます。

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: p_fo (pageFirstOnly) v3.0 (Requires AppMeasurement) */
function p_fo(c){if("-v"===c)return{plugin:"p_fo",version:"3.0"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c){a=b;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.p_fo="3.0");window.__fo||(window.__fo={});if(window.__fo[c])return!1;window.__fo[c]={};return!0};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## プラグインの使用

`p_fo` 関数は次の引数を使用します。

* **On**（必須、文字列）：プラグインが作成する JavaScript オブジェクトの名前です（オブジェクトがまだページに存在しない場合）。

オブジェクトが存在しない場合、この関数は `true` を返してオブジェクトを作成します。オブジェクトが既に存在する場合、この関数は `false` を返します。

## 呼び出しの例

### 例 1

次のコードは、ページ内に「myobject」オブジェクトが存在するかどうかを確認します。「Myobject」オブジェクトが存在しない場合、コードは「myobject」オブジェクトを作成し、true の値を返します。その結果、条件文内のコード（Console.log(&#39;hello&#39;)；）が実行されます。

一方、p_fo が呼び出された際に「myobject」オブジェクトが既に存在する場合、p_fo 関数は false の値を返し、条件文は false と見なされます。この場合、条件分内のコードは実行されません。

```js
if(p_fo("myobject"))
{
  console.log("hello");
}
```

**注意：**&#x200B;新しいページオブジェクト／DOM が読み込まれる（または現在のページがリロードされる）たびに、on 引数で指定されたオブジェクトは存在しなくなり、ページの読み込みが完了した後初めて実行されたときに、p_fo プラグインは再び true を返します。

## バージョン履歴

### 3.0 （2021 年 3 月 19 日（PT））

* コンテキストデータとしてバージョン番号を追加しました。

### 2.0

* ポイントリリース（再コンパイル、コードサイズの縮小）。
* 戻り値の型を整数からブール値に変更しました。

### 1.0

* 初回リリース。
