---
description: Activity Map でのリンクトラッキングに関するよくある質問（FAQ）です。
title: リンクトラッキングの FAQ
uuid: 10172073-b98b-4950-8397-67a18b37b3b4
feature: Activity Map
role: User, Admin
exl-id: b6ccdf91-98ce-413f-842d-c5423598ed49
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '518'
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

## リンクトラッキングはいつおこなわれますか？

Activity Mapリンクと地域の識別は、ユーザーがページをクリックしたときに発生します。

## デフォルトでは何が追跡されますか？

要素に対してクリックイベントが発生した場合、その要素はいくつかのチェックに合格し、AppMeasurementが要素をリンクとして処理するかどうかを判断する必要があります。 チェックは以下のとおりです。

* `href`プロパティを持つ`A`タグか`AREA`タグか。
* `s_objectID`変数を設定する`onclick`属性はありますか。
* これは、値または子テキストを持つ`INPUT`タグまたは`SUBMIT`ボタンですか？
* これは、型`IMAGE`と`src`プロパティを持つ`INPUT`タグですか？
* これは`BUTTON`ですか？

上記のいずれかの質問に対する答がはいの場合、要素はリンクとして処理され、追跡されます。

>[!IMPORTANT]
>
>AppMeasurementでは、属性type=&quot;button&quot;を持つbuttonタグは、リンクと見なされません。 buttonタグからtype=&quot;button&quot;を削除し、代わりにrole=&quot;button&quot;またはsubmit=&quot;button&quot;を追加することを検討してください。

>[!IMPORTANT]
>
>「#」で始まる「href」を含むアンカータグは、リンクではなく、AppMeasurementによって内部のターゲット位置と見なされます（ページを離れないので）。 デフォルトでは、Activity Map は、これらの内部のターゲット場所を追跡しません。ユーザーを新しいページにナビゲートするリンクのみを追跡します。

## Activity Mapは、その他の視覚的HTML要素をどのように追跡しますか。

a.`s.tl()`関数を使用。

クリックが`s.tl()`の呼び出しを通じて発生した場合、Activity Mapもこのクリックイベントを受け取り、`linkName`文字列変数が見つかったかどうかを判断します。 `s.tl()`の実行中に、そのlinkNameがActivity MapリンクIDとして設定されます。 `s.tl()`呼び出しを発生させたクリックされた要素を使用して、領域が特定されます。 例：

```
<img onclick="s.tl(true,'o','abc')" src="someimageurl.png"/>
```

b.`s_objectID`変数を使用。 例：

    &quot;&#39; 
    
    &lt;a>&lt;img>&lt;/a>
    
    &lt;a>Link Text Here&lt;/a>
    
    
    &quot;&#39;

>[!IMPORTANT]
>
>Activity Mapで`s_objectID`を使用する場合は、末尾のセミコロン(;)が必要です。

## 追跡されるリンクの例をいくつか教えてください。

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

## 追跡されないリンクの例をいくつか示してください。

1. 理由：アンカータグに有効な`href`がありません：
   `<a name="innerAnchor">Section header</a>`

1. 理由：`s_ObjectID`も`s.tl()`も存在しません：

   ```
   <p onclick="showPanel('market rates')">
     <span class="title">Current Market Rates</span>
     <span class="subtitle">1.45USD</span>
   </p>
   ```

1. 理由：`s_ObjectID`も`s.tl()`も存在しません：

   ``` 
   <input type="radio" onclick="changeState(this)" name="group1" value="A"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="B"/>
   <input type="radio" onclick="changeState(this)" name="group1" value="C"/>
   
   ```  
   
1. 理由：&quot;src&quot;プロパティにフォーム入力要素がない：

   `<input type="image"/>`
