---
title: 内部トラフィック
description: 内部トラフィックプラグインは、内部ネットワークからの訪問者を動的に識別します。
seo-description: 内部トラフィックプラグイン
seo-title: 内部トラフィックプラグイン
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# 内部トラフィック

内部トラフィックプラグインは、内部ネットワークからの訪問者を動的に識別します。

内部トラフィックと外部トラフィックを識別することで、収集するデータをフィルタリングおよびセグメント化するメカニズムを提供し、あらゆるタイプのレポートの精度を向上させます。また、適切に導入すると、トラフィックを識別する一般的なアプローチである、VISTA ルールや処理ルールを使用する必要がなくなります。

## 内部トラフィックプラグインはどのように機能しますか。

プラグインは、1x1 の透過ピクセルなど、内部ネットワーク／イントラネット内でのみ使用できるファイルの読み込みを試みます。読み込みが成功した場合、その訪問者のトラフィックは内部トラフィックとして識別されます。それ以外はすべて、外部トラフィックです。

## 注意点

* このアプローチの唯一の欠点として、外部訪問者が訪問した最初のページで、ブラウザーコンソールに 404 エラーが表示されます。これは、ユーザーエクスペリエンスには影響しません。
* 内部でホストされるピクセルを読み込む前に、ネットワークチームまたは情報セキュリティチームから承認を得ることを強くお勧めします。
* プラグインは、（VISTA ルールでおこなわれるように）トラフィックを別のレポートスイートに移したり、レポートから除外したりするわけではありませんが、カスタムロジックを実装に含めて、この機能をクライアント側で実行できるようにします。

## 実装

1. イントラネットピクセルの追加：プラグインがアクセスを試みるイントラネット上に、任意の種類のファイルを追加できます。1 x 1 の透過ピクセルを使用することをお勧めします。内部ネットワーク内から広くアクセス可能なイントラネット上の場所に配置する必要があります。
1. eVar の設定：eVar は、宛先レポートスイート内に追加する必要があります。「訪問」の有効期限と「元の値（最初）」の配分が必要です。
1. 内部 URL の定義：AppMeasurement 設定変数内、および doPlugins がインスタンス化される前に、ピクセルまたは他のファイルの内部 URL 変数（s.intURL）をトラフィックチェックに使用できるように定義します。例：`s.intURL = "https://www.yourdomainhere.com/trafficCheck.gif"`
1. Modify doPlugins and set the eVar: The plugin can then be initialized by including this line of code within the doPlugins section of your AppMeasurement library code, using the eVar defined in step one: `s.eVarXX = s.intCheck();`
The variable value will be set to "internal" or "external".
1. プラグインソースコードの追加：AppMeasurement ファイルの doPlugins セクションの下にプラグインコードを含めます。

## プラグインのソースコード

このコードを AppMeasurement ライブラリの doPlugins セクションの下に追加します。

```JavaScript
s.intCheck=new Function("",""
+"var s=this;if(document.cookie.indexOf('intChk=')==-1){try{document."
+"cookie='intChk=1';var x=new XMLHttpRequest(),y;x.open('GET',s.intUr"
+"l,false);x.send();if(x.status===200&&x.statusText==='OK'){y='intern"
+"al';}}catch(e){y='external'}finally{return y}}");
```

## その他のメモ

* 必ず、プラグインでデータの収集が希望どおりに実行されることをテストし確認してから、実稼動環境に実装してください。
* 実装では、デフォルトの Adobe Analytics "s" オブジェクト以外のオブジェクト名を使用できます。その場合は適切なオブジェクト名に変更してください。
* タグ管理システムを採用する場合は、その手順に従って doPlugins と他のカスタムプラグインを更新してください。
