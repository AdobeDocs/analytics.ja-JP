---
description: getAndPersistValue プラグインは、選択した値を取得し、指定の期間にわたって Analytics 変数に設定します。一般的には、キャンペーンでどれだけ多くのページビューがクリックスルー後に生成されたかを確認するために使用されます。これにより、各キャンペーンで最も一般的なページを容易に知ることができます。
keywords: Analytics の導入
seo-description: getAndPersistValue プラグインは、選択した値を取得し、指定の期間にわたって Analytics 変数に設定します。一般的には、キャンペーンでどれだけ多くのページビューがクリックスルー後に生成されたかを確認するために使用されます。これにより、各キャンペーンで最も一般的なページを容易に知ることができます。
seo-title: getAndPersistValue
solution: Analytics
subtopic: プラグイン
title: getAndPersistValue
topic: 開発者と導入
uuid: ddeab80c-260e-44b6-8483-8b8b369ec19b
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getAndPersistValue

getAndPersistValue プラグインは、選択した値を取得し、指定の期間にわたって Analytics 変数に設定します。一般的には、キャンペーンでどれだけ多くのページビューがクリックスルー後に生成されたかを確認するために使用されます。これにより、各キャンペーンで最も一般的なページを容易に知ることができます。

>[!IMPORTANT]
>
>This plug-in has not been validated to be compatible with [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8). [AppMeasurementプラグインのサポート](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A)を参照してください。

For example, you might use this plug-in to set a campaign tracking code from the *`campaign`* variable into a Custom Traffic ( *`s.prop`*) variable on each visitor's page view made for the next 30 days. この例では、元のクリックスルーによってトラッキングコードが生成したページビューの数を特定できます。

>[!NOTE]
>
>次の手順では、サイトのデータ収集コードを変更する必要があります。変更は、サイトでのデータ収集に影響が及ぶ可能性があるので、[!DNL Analytics] の使用と導入の経験がある開発者のみがおこなうようにしてください。

## プラグインコードと導入 {#section_92E94A96A4764113B5588F1B83E3DE2C}

**CONFIG SECTION**：このセクションでは変更は必要ありません。

**プラグイン構成**

次のコードを *`s_doPlugins()`* 関数 *`s_code.js`***&#x200B;を使用します。持続値データを取り込むために、1 つのカスタムトラフィック（s.prop）変数または 1 つのカスタムコンバージョン（s.eVar）変数を選択します。これは Admin Console を使って有効にした変数で、他の目的では使用されていないものを使います。次のサンプルは自分の条件に合わせて変更して使用できます。

`s.prop1=s.getAndPersistValue(s.campaign,'s_getval',30);`

*`s.getAndPersistValue`* には 3 つの引数があります。

1. Currently populated variable or value to persist ( *`s.campaign`* shown above).
1. Cookie name, used to store the value ( *`s_getval`* shown above).
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
