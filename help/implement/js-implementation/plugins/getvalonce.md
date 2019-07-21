---
description: getValOnce プラグインは、特定の変数が以前に定義された値に設定されないようにします。これは、cookie を使用して変数の最後の表示値を判断します。現在の値が cookie の値と一致する場合、その変数はブランク文字列で上書きされた後でアドビの処理サーバーに送信されます。このプラグインは、ユーザーがページをリフレッシュした場合または「戻る」ボタンをクリックした場合に、コンバージョン変数のインスタンスが膨張するのを防ぐのに役立ちます。
keywords: Analytics の導入
seo-description: getValOnce プラグインは、特定の変数が以前に定義された値に設定されないようにします。これは、cookie を使用して変数の最後の表示値を判断します。現在の値が cookie の値と一致する場合、その変数はブランク文字列で上書きされた後でアドビの処理サーバーに送信されます。このプラグインは、ユーザーがページをリフレッシュした場合または「戻る」ボタンをクリックした場合に、コンバージョン変数のインスタンスが膨張するのを防ぐのに役立ちます。
seo-title: getValOnce
solution: Analytics
subtopic: プラグイン
title: getValOnce
topic: 開発者と導入
uuid: 82fe0da5-3bc4-4632-8c62-7b5683f6b587
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getValOnce

getValOnce プラグインは、特定の変数が以前に定義された値に設定されないようにします。これは、cookie を使用して変数の最後の表示値を判断します。現在の値が cookie の値と一致する場合、その変数はブランク文字列で上書きされた後でアドビの処理サーバーに送信されます。このプラグインは、ユーザーがページをリフレッシュした場合または「戻る」ボタンをクリックした場合に、コンバージョン変数のインスタンスが膨張するのを防ぐのに役立ちます。

>[!IMPORTANT]
>
>This plug-in has not been validated to be compatible with [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8). [AppMeasurementプラグインのサポート](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A)を参照してください。

**パラメーター**

```js
s.eVar1=s.getValOnce(variable,cookie,expiration,minute);
```

* **Variable：**&#x200B;確認される変数です。これは通常、定義されている変数と同じです。
* **Cookie：**&#x200B;比較対象である以前の値を保持する cookie の名前です。cookie は任意の値です。
* （オプション）**Expiration：** cookie の有効期限が切れる日数です。設定されない、または 0 に設定された場合、デフォルトの有効期限はブラウザーのセッションとなります。
* （オプション）**Minute：**&#x200B;これを文字列の値 *`m`*&#x200B;の場合、有効期限の値は日数ではなく分数で定義されます。If not set, *`days`* is the default expiration.

**プロパティ**

* このプラグインは一般にコンバージョン変数に使われます。ただし、任意の [!DNL Analytics] 変数で使用することができます。
* JavaScript がこの関数に遭遇すると、定義された値と cookie に保存されている値とが比較されます。定義された値が cookie の値と異なる場合、定義された値が設定されます。定義された値が cookie の値と同じである場合、空白の文字列が返されます。
* cookie は単一の値しか保存できません。つまり、プラグインは最後に定義された値しか見ることができません。
* プラグインでは、変数が定義された後、すべての値で変数が定義されるのを防ぐわけではありません。プラグインは、前の値で連続して何度も設定されるのを防ぐだけです。
* エンドユーザーが cookie をブロックまたは拒否した場合、元の値が常に返されます。
* プラグインのセッションは、[!DNL Analytics] が定義するセッション（または訪問）とは異なります。[!DNL Analytics] は、12 時間の操作状態または 30 分間の無操作状態が続くとセッションを停止します。プラグインはブラウザーのセッション定義を使用するので、ユーザーがタブを閉じるかブラウザーを閉じた場合にのみセッションを停止します。

   * ユーザーがサイトのページを閉じた後、別のタブを開いて 30 分以内に再度サイトにアクセスすると、プラグインでは新たなセッションを作成しますが、[!DNL Analytics] の訪問は開いたままになります。
   * ユーザーがブラウザーウィンドウを開いたまま 30 分間リンクをクリックしなかった場合、[!DNL Analytics] の訪問は有効期限が切れますが、ブラウザーセッションは開いたままになります。

>[!NOTE]
>
>次の手順では、サイトのデータ収集コードを変更する必要があります。変更は、サイトでのデータ収集に影響が及ぶ可能性があるので、[!DNL Analytics] の使用と導入の経験がある開発者のみがおこなうようにしてください。

## 実装 {#section_177FF7F425B64FFB83CDE15A6ACC8D21}

>[!NOTE]
>
>If your organization uses Marketing Channels and has rules set up based on `s.campaign`, it is recommended that you not use the getValOnce plugin when setting the `s.campaign`value. このプラグインを使用すると、二次的なキャンペーンのクリックスルーに間違ったチャネルが割り当てられる場合があります。

このプラグインを導入するには、次のコードを [!DNL s_code.js] ファイル内に置きます。

```js
/******************************************************************** 
 * 
 * Main Plug-in code (should be in Plug-ins section) 
 * 
 *******************************************************************/ 
/* 
 * Plugin: getValOnce_v1.11 
 */ 
s.getValOnce=new Function("v","c","e","t","" 
+"var s=this,a=new Date,v=v?v:'',c=c?c:'s_gvo',e=e?e:0,i=t=='m'?6000" 
+"0:86400000,k=s.c_r(c);if(v){a.setTime(a.getTime()+e*i);s.c_w(c,v,e" 
+"==0?0:a);}return v==k?'':v");
```

Once the above code is implemented, define the desired variable using the *`getValOnce`* function. 次は導入のいくつかの例です。

**cookie が設定されてから 30 日未満で重複する値が検知された場合に、同じキャンペーン値が定義されるのを防ぎます。**`s.campaign=s.getValOnce(s.campaign,'s_cmp',30);`**cookieが設定されてから30分以内に重複値が検出された場合、同じeVar1値が定義されないようにします。**`s.eVar1=s.getValOnce(s.eVar1,'s_ev1',30,'m');`**同じブラウザセッションで同じeVar2値が複数回定義されないようにします。**`s.eVar2=s.getValOnce(s.eVar2,'s_ev2');`**メモ**

* 必ず、プラグインでデータの収集が希望どおりに実行されることを十分にテストし確認してから、実稼動環境に実装してください。
* テストでは cookie を削除するか、新しい固有値を使用してください。そうでないと、変数が送信されません。

