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
ht-degree: 100%

---

# リンクトラッキングの FAQ

Activity Map でのリンクトラッキングに関するよくある質問（FAQ）です。

>[!CAUTION]
>
>Activity Map トラッキングをオンにすると、**個人を特定できる情報（PII）のデータを収集できます。** このデータは、そのまま使用するか、その他の情報と共に使用して、個人を特定および検索したり、個人と連絡を取ったり、コンテキスト内で個人を特定したりすることができます。

Activity Map トラッキングによって PII データが収集される可能性がある既知のケースには次のようなものがあります。

* `Mailto` リンク。mailto リンクは、メールを送信するためにコンピューター上のデフォルトのメールクライアントを起動するの HTML リンクです。
* `User ID` リンク。ユーザーがログインすると、Web サイトのヘッダー／フッターに表示される場合があります。
* 金融機関では、口座番号がリンクとして表示されている場合があります。そのリンクをクリックすると、リンクのテキストが収集されます。
* また、医療関連の Web サイトでも、PII データがリンクとして表示されている場合があります。これらのリンクをクリックすると、リンクのテキストが収集されるので、PII データが収集されることになります。

## リンクトラッキングはいつ行われますか？

Activity Map のリンクと領域の識別は、ユーザーがページをクリックしたときに行われます。

## デフォルトでは何がトラッキングされますか？

要素でクリックイベントが発生した場合、その要素は、AppMeasurement がそれをリンクとして扱うかどうかを判断するためにいくつかのチェックに合格する必要があります。チェックは次のとおりです。

* これは `href` プロパティを持つ `A` または `AREA` タグか
* `s_objectID` 変数を設定する `onclick` 属性があるか
* これは、値または子テキストを持つ `INPUT` タグまたは `SUBMIT` ボタンか
* これは、type が `IMAGE` で `src` プロパティを持つ `INPUT` タグか
* これは `BUTTON` か

上記の質問のいずれかに対する答えが「はい」の場合、要素はリンクとして扱われ、トラッキングされます。

>[!IMPORTANT]
>
>属性 type=&quot;button&quot; を持つボタンタグは、AppMeasurement ではリンクとは見なされません。ボタンタグの type=&quot;button&quot; を削除し、代わりに role=&quot;button&quot; または submit=&quot;button&quot; を追加することを検討してください。

>[!IMPORTANT]
>
>AppMeasurement では、「#」で始まる「href」を含むアンカータグは、リンクではなく、内部ターゲット場所と見なされます（ページを離れないので）。デフォルトでは、Activity Map は、これらの内部のターゲット場所を追跡しません。ユーザーを新しいページにナビゲートするリンクのみを追跡します。

## Activity Map では、他のビジュアル HTML 要素はどのようにトラッキングされますか？

a. `s.tl()` 関数を使用します。

クリックが `s.tl()` 呼び出しを介して発生した場合、Activity Map もこのクリックイベントを受け取り、`linkName` 文字列変数が見つかったかどうかを判断します。`s.tl()` の実行時に、その linkName が Activity Map のリンク ID として設定されます。`s.tl()` 呼び出しが発生したクリックされた要素は、領域を特定するために使用されます。例：

```
<img onclick="s.tl(true,'o','abc')" src="someimageurl.png"/>
```

b. `s_objectID` 変数を使用します。例：

    ``` 
    
    &lt;img onclick=&quot;s_objectID=&#39;abc&#39;;&quot; src=&quot;someimageurl.png&quot;/>
    &lt;a href=&quot;some-url.html&quot; onclick=&quot;s_objectID=&#39;abc&#39;;&quot; >
    ここにテキストをリンク
    &lt;/a>
    
    ```

>[!IMPORTANT]
>
>Activity Map で `s_objectID` を使用する場合、末尾のセミコロン（;）は必須です。

## トラッキングされるリンクの例をいくつか示してください。

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

## トラッキングされないリンクの例をいくつか示してください。

1. 理由：アンカータグに有効な `href` が含まれていない
   `<a name="innerAnchor">Section header</a>`

1. 理由：`s_ObjectID` も `s.tl()` も存在しない

   ```
   <p onclick="showPanel('market rates')">
     <span class="title">Current Market Rates</span>
     <span class="subtitle">1.45USD</span>
   </p>
   ```

1. 理由：`s_ObjectID` も `s.tl()` も存在しない

   ``` 
   <input type="radio" onclick="changeState(this)" name="group1" value="A"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="B"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="C"/>
   
   ```  
   
1. 理由：「src」プロパティにフォーム入力要素がない

   `<input type="image"/>`

