---
description: Analytics コードによりイメージオブジェクトが作成されます。これは、ページ上には表示されないイメージです。
keywords: Analytics の実装
seo-description: Analytics コードによりイメージオブジェクトが作成されます。これは、ページ上には表示されないイメージです。
seo-title: head タグへの Analytics コードの配置
solution: Analytics
title: head タグへの Analytics コードの配置
topic: 開発者と実装
uuid: e8f91d3c-cb72-454d-9bd4-ff54d83d981f
translation-type: ht
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# head タグへの Analytics コードの配置

Analytics コードによりイメージオブジェクトが作成されます。これは、ページ上には表示されないイメージです。

>[!NOTE]
>
>この節の説明は、s_code.js によるレガシー導入にのみ当てはまります。[JavaScript 版 AppMeasurement 1.0](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8) では、`<head>` タグへのライブラリおよびページコードのデプロイがサポートされます。

これまでは、Analytics JavaScript コードを <head><meta http-equiv="Content-Type" content="text/html; charset=UTF-8"> と </head> タグの間に配置する導入方法が一般的でした。この 2 つのタグの間にコードを配置すると、Adobe サーバーにデータを送信した要求から 1 x 1 ピクセルの画像が返された際に、ページレイアウトに影響しなくなります。また、ドキュメントの head 部分にコードを配置すると、コードが早く出現することになります。したがって、コードは早い段階で実行され、部分的なページ読み込みのページビューをより効果的にカウントできます。

コードの特定の要素には body オブジェクトが必要です。Web ブラウザーはコードを受け取った順に実行するので、ドキュメントの head 部分にある Analytics JavaScript コードは body オブジェクトの前に実行されます。その結果、導入では [!UICONTROL ClickMap] データが収集されず、ファイルのダウンロード数または[!UICONTROL 離脱]リンクの自動トラッキングは使用できません。また、接続タイプデータや訪問者のホームページデータも送信されません。ドキュメントの head にコードを配置すると便利ですが、非常に限られたバージョンの Analytics でしか成果は得られず、[!UICONTROL ClickMap] を含む一部のレポートやツールでデータが記録されないので疑問に思うこともあるでしょう。

Analytics コードは、整形式 HTML ページの BODY タグ（<BODY></BODY>）内に含める必要があります。ページ先頭（HTML の body タグ内）にあるグローバルインクルードファイルにコードを配置することを推奨します。以下の場合を除き、ページの任意の場所にコードを配置できます。

* テーブル内では、 <td></td> タグ内にのみコードを配置してください。例えば、開始 <tr> タグと開始 <td> タグの間にはコードを配置しないでください。
* 変数を設定するコードは、s_code.js ファイルへの参照の後に配置する必要があります。
* s_code.jsファイル内の *`s_account`* 変数で [!UICONTROL レポートスイート ID ]が正しく設定されていることを確認します。通常、この変数は、特定のレポートスイート用のコードをコードマネージャーからダウンロードする場合、またはアドビのテクニカルコンサルタントの指示に従って正しく設定します。

Analytics を Target と統合する場合は、JavaScript インクルードファイルをページの末尾に配置する必要があります。次の例は、Analytics コードの正しい配置を示しています。

```js
<html> 
<head></head> 
<body> 
<!-- Analytics code version: H.20.3. 
Copyright 1997-2009 Omniture, Inc. More info available at 
https://www.omniture.com --> 
<script language="JavaScript" type="text/javascript" src="https://www.yourdomain.com/js/s_code.js"></script> 
<script language="JavaScript" type="text/javascript"><!-- 
/* You may give each page an identifying name, server, and channel on 
the next lines. */ 
s.pageName="" 
s.server="" 
s.channel="" 
s.pageType="" 
s.prop1="" 
s.prop2="" 
s.prop3="" 
s.prop4="" 
s.prop5="" 
/* Conversion Variables */ 
s.campaign="" 
s.state="" 
s.zip="" 
s.events="" 
s.products="" 
s.purchaseID="" 
s.eVar1="" 
s.eVar2="" 
s.eVar3="" 
s.eVar4="" 
s.eVar5="" 
/************* DO NOT ALTER ANYTHING BELOW THIS LINE ! **************/ 
var s_code=s.t();if(s_code)document.write(s_code)//--></script> 
<!-- End Analytics code version: H.20.3. --> 
</body> 
</html> 
```

