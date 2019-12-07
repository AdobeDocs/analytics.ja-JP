---
description: getAndPersistValue プラグインは、選択した値を取得し、指定の期間にわたって Analytics 変数に設定します。一般的には、キャンペーンでどれだけ多くのページビューがクリックスルー後に生成されたかを確認するために使用されます。これにより、各キャンペーンで最も一般的なページを容易に知ることができます。
keywords: Analytics Implementation
subtopic: Plug-ins
title: getAndPersistValue
topic: Developer and implementation
uuid: ddeab80c-260e-44b6-8483-8b8b369ec19b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getAndPersistValue

getAndPersistValue プラグインは、選択した値を取得し、指定の期間にわたって Analytics 変数に設定します。一般的には、キャンペーンでどれだけ多くのページビューがクリックスルー後に生成されたかを確認するために使用されます。これにより、各キャンペーンで最も一般的なページを容易に知ることができます。

>[!IMPORTANT]
>
>このプラグインは、[JavaScript 版 AppMeasurement](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md) との互換性が検証されていません。[AppMeasurement プラグインのサポート](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md)を参照してください。

例えば、このプラグインを使用して、次の 30 日間におこなわれた各訪問者のページビューで、*`campaign`* 変数のキャンペーントラッキングコードをカスタムトラフィック（*`s.prop`*）変数に設定することができます。この例では、元のクリックスルーによってトラッキングコードが生成したページビューの数を特定できます。

> [!NOTE]後述の説明では、実際のサイトに合わせてデータ収集コードを変更する必要があります。変更は、サイトでのデータ収集に影響が及ぶ可能性があるので、[!DNL Analytics] の使用と導入の経験がある開発者のみがおこなうようにしてください。

## プラグインコードと導入 {#section_92E94A96A4764113B5588F1B83E3DE2C}

**CONFIG SECTION**：このセクションでは変更は必要ありません。

**プラグイン構成**

次のコードを *`s_doPlugins()`* 関数内に置いてください。この関数は、*`s_code.js`ファイルの* Plugin Config *という名称の領域にあります。*&#x200B;持続値データを取り込むために、1 つのカスタムトラフィック（s.prop）変数または 1 つのカスタムコンバージョン（s.eVar）変数を選択します。これは Admin Console を使って有効にした変数で、他の目的では使用されていないものを使います。次のサンプルは自分の条件に合わせて変更して使用できます。

`s.prop1=s.getAndPersistValue(s.campaign,'s_getval',30);`

*`s.getAndPersistValue`* には 3 つの引数があります。

1. 現在設定されている変数または残す値（上記 *`s.campaign`* を参照）。
1. cookie名。値の保存に使用されます（上記の *`s_getval`*）。
1. 持続の期間（日数）。上記の「30」では、今後 30 日間、ユーザーがおこなうすべてのページビューで、指定した変数に値が入力されます。空白の場合、設定はデフォルトで *session* となります。

**PLUGINS SECTION**：[!DNL s_code.js] ファイルにある PLUGINS SECTION という名称の領域に次のコードを追加します。プラグインコードのこの部分は一切変更しないでください。

```js
/* 
 * Plugin: getAndPersistValue 0.3 - get a value on every page 
 */ 
s.getAndPersistValue=new Function("v","c","e","" 
+"var s=this,a=new Date;e=e?e:0;a.setTime(a.getTime()+e*86400000);if(" 
+"v)s.c_w(c,v,e?a:0);return s.c_r(c);");
```

必ず、プラグインでデータの収集が希望どおりに実行されることを十分にテストし確認してから、実稼動環境に実装してください。
