---
description: Activity Map でのリンクトラッキングに関するよくある質問（FAQ）です。
title: リンクトラッキングの FAQ
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
feature: Activity Map
role: User, Admin
exl-id: b6ccdf91-98ce-413f-842d-c5423598ed49
source-git-commit: 2a20ce50f773c82856da59154bb212f1fca2b7ea
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 43%

---

# リンクトラッキングの FAQ

Activity Map でのリンクトラッキングに関するよくある質問（FAQ）です。

>[!CAUTION]
>
>Activity Map トラッキングをオンにすると、**個人を特定できる情報（PII）のデータを収集できます。**&#x200B;このデータは、そのまま使用するか、その他の情報と共に使用して、個人を特定および検索したり、個人と連絡を取ったり、コンテキスト内で個人を特定したりすることができます。

Activity Map トラッキングによって PII データが収集される可能性がある既知のケースには次のようなものがあります。

* `Mailto` リンク。mailto リンクは、メールを送信するためにコンピューター上のデフォルトのメールクライアントを起動するの HTML リンクです。
* `User ID` リンク。ユーザーがログインすると、Web サイトのヘッダー／フッターに表示される場合があります。
* 金融機関では、口座番号がリンクとして表示されている場合があります。そのリンクをクリックすると、リンクのテキストが収集されます。
* また、医療関連の Web サイトでも、PII データがリンクとして表示されている場合があります。これらのリンクをクリックすると、リンクのテキストが収集されるので、PII データが収集されることになります。

## リンク追跡はいつ実行されるか。

アクティビティマップへのリンクおよび地域の識別は、ユーザーがページをクリックしたときに実行されます。

## デフォルトでトラッキングされる内容

エレメントに click イベントが発生した場合、そのエレメントは、AppMeasurement によってそのエレメントがリンクとして扱われるかどうかを判断するために、何らかのチェックを通す必要があります。 チェックは以下のとおりです。

* これは、 `A` `AREA` プロパティと共に or タグになり `href` ます。
* `onclick`変数を設定する属性がある `s_objectID` かどうかを確認します。
* これは `INPUT` `SUBMIT` 、値または子のテキストが付いたタグまたはボタンですか?
* これは、 `INPUT` タイプおよびプロパティが設定されたタグ `IMAGE` `src` かどうかを示します。
* これは a `BUTTON` ?

上記のいずれかの質問に対する答がはいの場合、要素はリンクとして処理され、追跡されます。

>[!IMPORTANT]
>
>属性タイプが「button」である button タグは、AppMeasurement によってリンクされるとは見なされません。 代わりに button タグ上の type = 「button」を削除し、role = 「button」または submit = &quot;button&quot; を追加することを検討してください。

>[!IMPORTANT]
>
>「Href」によって開始されたアンカータグは、リンクではなく、(ページから移動しないと) AppMeasurement によって、内部ターゲットの場所として扱われます。 デフォルトでは、Activity Map は、これらの内部のターゲット場所を追跡しません。ユーザーを新しいページにナビゲートするリンクのみを追跡します。

## アクティビティマップでのその他の視覚的な HTML エレメントの追跡方法

に.この関数を使用 `s.tl()` します。

呼び出しによって click が発生した場合は `s.tl()` 、アクティビティーマップによって click イベントが表示され、ストリング変数が検出されたかどうかが確認され `linkName` ます。 実行時に `s.tl()` 、その linkName がアクティビティマップリンク ID として設定されます。 呼び出しを開始した要素は、 `s.tl()` 地域を決定するために使用されます。 例：

```
<img onclick="s.tl(true,'o','abc')" src="someimageurl.png"/>
```

b.変数を使用 `s_objectID` します。 例：

    「ここに 
    
     &lt;img onclick=&quot;s_objectID=&#39;abc&#39;;&quot; src=&quot;someimageurl.png&quot;/> 
     &lt;a href=&quot;some-url.html&quot; onclick=&quot;s_objectID=&#39;abc&#39;;&quot; > 
     テキストをリンク 
     
    
     」というテキストを入力します。 
 &lt;/a href=&quot;some-url.html&quot; onclick=&quot;s_objectID=&#39;abc&#39;;&quot; >
>[!IMPORTANT]
>
>後続するセミコロン (;)は、アクティビティマップでを使用する場合に必要です `s_objectID` 。

## トラックされるリンクの例には、どのようなものがありますか。

### 例 1

```
  <a hef="/home?lang=en>Home</a>
```

### 例 2

```
 <input type="submit" value="Submit"/>
```

### 例 3

```
  <input type="image" src="submit-button.png"/>
```

### 例 4

```
    <p onclick="var s_objectID='custom link id';">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </p>
```

### 例 5

```
    <div onclick="s.tl(true,'o','custom link id')">
      <span class="title">Current Market Rates</span>
      <span class="subtitle">1.45USD</span>
    </div>
```

## トラックされないリンクについては、いくつかの例を示してもかまいません。

1. 理由: アンカータグに、次の有効な値がありません `href` 。
   `<a name="innerAnchor">Section header</a>`

1. 理由: `s_ObjectID` または表示されること `s.tl()` はありません。

   ```
   <p onclick="showPanel('market rates')">
     <span class="title">Current Market Rates</span>
     <span class="subtitle">1.45USD</span>
   </p>
   ```

1. 理由: `s_ObjectID` または表示されること `s.tl()` はありません。

   ``` 
   <input type="radio" onclick="changeState(this)" name="group1" value="A"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="B"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="C"/>
   
   ```  
   
1. 理由: &quot;src&quot; プロパティにフォームの input エレメントがありません。

   `<input type="image"/>`

