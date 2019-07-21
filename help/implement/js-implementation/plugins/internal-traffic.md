---
title: 内部トラフィック
description: Internal Trafficプラグインは、内部ネットワークからの訪問者を動的に識別します。
seo-description: Internal Traffic plugin
seo-title: Internal Traffic plugin
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# 内部トラフィック

Internal Trafficプラグインは、内部ネットワークからの訪問者を動的に識別します。

内部トラフィックと外部トラフィックを識別することで、収集されるデータをフィルタおよびセグメント化するメカニズムを提供することで、あらゆるタイプのレポートの精度を向上します。これにより、VISTAルールや処理ルールが不要になり、これらのトラフィックを識別するための一般的な方法が不要になります。

## 内部トラフィックプラグインはどのように機能しますか。

プラグインは、内部ネットワーク/イントラネット内でのみ利用可能なファイルの読み込み（1x1ピクセルの透過ピクセル）を試みます。正常に読み込まれた場合、その訪問者のトラフィックは内部で識別されます。その他すべてのトラフィックは外部トラフィックになります。

## 注意点

* このアプローチの欠点は、404エラーが、訪問の最初のページにある外部訪問者のブラウザーコンソールに表示される点です。これは、ユーザーエクスペリエンスには影響しません。
* 内部的にホストされるピクセルを読み込む前に、ネットワークまたはinfoSecチームから承認を取得することを強くお勧めします。
* プラグインはトラフィックを別のレポートスイートに移動したり、レポートから除外したりすることはできません（VISTAルールによって実行される可能性もあります）。これにより、この機能がクライアント側を実行できるように、カスタムロジックを実装に含めることができます。

## 実装

1. イントラネットピクセルの追加:プラグインでアクセスしようとしたイントラネットに任意のタイプのファイルを追加できます。1x1透明ピクセルを使用することをお勧めします。社内ネットワーク内から広くアクセスできるイントラネット上の場所に配置する必要があります。
1. eVarの設定:宛先レポートスイート内にeVarを追加する必要があります。「訪問」と「オリジナル値（最初）」の配分が有効である必要があります。
1. 内部URLの定義:AppMeasurement設定変数内およびdoPluginsのインスタンス化の前に、トラフィックチェックに使用できるピクセルまたはその他のファイルの内部URL変数（s. intURL）を定義します。例えば、`s.intURL = "https://www.yourdomainhere.com/trafficCheck.gif"`
1. Modify doPlugins and set the eVar: The plugin can then be initialized by including this line of code within the doPlugins section of your AppMeasurement library code, using the eVar defined in step one: `s.eVarXX = s.intCheck();`
The variable value will be set to “internal” or “external”.
1. プラグインソースコードの追加:プラグインコードをAppMeasurementファイルのdoPluginsセクションの下に含めます。

## プラグインソースコード

AppMeasurementライブラリのdoPluginsセクションの下にこのコードを追加します。

```s.intCheck=new Function("",""
+"var s=this;if(document.cookie.indexOf('intChk=')==-1){try{document."
+"cookie='intChk=1';var x=new XMLHttpRequest(),y;x.open('GET',s.intUr"
+"l,false);x.send();if(x.status===200&&x.statusText==='OK'){y='intern"
+"al';}}catch(e){y='external'}finally{return y}}");```

## Other Notes

* Always test plug-in installations to ensure that data collection happens as expected before deploying them in a production environment.
* Your implementation might be using a different object name than the default Adobe Analytics "s" object. If so, please update the object name accordingly.
* If you employ a Tag Management System, please follow its steps to update doPlugins and the other custom plugins.

