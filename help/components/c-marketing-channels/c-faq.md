---
description: マーケティングチャネルに対して設定可能な様々なルールを入力するためのベストプラクティスと例をご確認ください。
title: マーケティングチャネルに関するFAQと例
translation-type: tm+mt
source-git-commit: 21f4b9df688776f7a1db96f76e258031ae3abb3d

---


# マーケティングチャネルに関するFAQと例

See [Create Marketing Channel Processing Rules](/help/components/c-marketing-channels/c-rules.md) for definitions of fields displayed on the [!UICONTROL Marketing Channel Processing Rules] page.

## よくある質問 {#faq}

マーケティングチャネルの処理ルールの実装は、トラッキングコードによって異なります。求める結果をもたらすようなルールを設定するには、問題を解決するための工夫が求められる場合があります。

**質問**：私のトラッキングコードはパターンに従っていません。また、アフィリエイトチャネル用に指定しなければならないコードが無数にあります。

* 除外処理を使用します。電子メールチャネルとアフィリエイトチャネルに同一のクエリ文字列パラメーターを使用しているとき、電子メールのトラッキングコードが少数なら、電子メールを定義するルールセットで電子メールトラッキングコードを指定することができます。その後、残りすべてのトラッキングコードをアフィリエイトとして分類します。 *`affiliates.`*
* 電子メールシステムで、ランディングページのすべての URL に *`&ch=eml`* などのクエリー文字列パラメーターを追加します。ch クエリパラメーターが *`eml`* と等しいかどうかを検出するルールセットを作成します。*`eml`* が含まれない場合はアフィリエイトです。

**質問**：参照ドメインに予想より多くのデータが含まれています。

* 参照ドメインが処理ルールリストで上位すぎる可能性があります。処理順序が重要なので、下位の方（または最下位）に配置してください。

**質問**：クエリー文字列パラメーターに一致するルールを作成しましたが、うまく機能しません。

* クエリー文字列パラメーターのフィールドでパラメーター名（通常は英数字の値）が指定されていることを確認してください。また、次の電子メールルールの例に示すように、演算子の後にパラメーター値が指定されていることを確認してください。

   ![](assets/example_email.png)

**質問**：ラストタッチトラフィックの属性がすべて内部ドメインになっているのはどうしてですか。

* 内部トラフィックに一致するルールがあります。これらのルールは訪問の最初のページだけでなく、サイト上のすべてのページビューで処理されることを忘れないでください。「*`Page URL exists`*」などのルールが指定されていて、他の条件が指定されていない場合は、ページの URL が常に存在するので、サイト上の連続するヒットのそれぞれについてそのチャネルが照合されます。

**質問**：レポートに「チャネルが識別されませんでした」と表示されているトラフィックは、どのようにデバッグしたらよいですか。

* ルールは順番に処理されます。以下のような場合は、どの条件にも一致しないことがあります。

1. リファラーなし（直接訪問）。

2. 内部リファラー、訪問の最初のページ。

3. ページの処理異常。

この 3 つの可能性用のチャネルを用意してください。例えば、次のようなルールを作成します。

1. **[!UICONTROL Referrer]** そして **[!UICONTROL Does Not Exist]** と **[!UICONTROL Is First Page of Visit]**&#x200B;を （[直接](/help/components/c-marketing-channels/c-faq.md)を参照）

2. **[!UICONTROL Referrer Matches Internal URL Filters]** と **[!UICONTROL Is First page of Visit]**. （[内部](/help/components/c-marketing-channels/c-faq.md)を参照）。

3. **[!UICONTROL Referrer]** そして **[!UICONTROL Exists]** と **[!UICONTROL Referrer Does Not Match Internal URL Filters]**&#x200B;を

最後に、[チャネルが識別されませんでした](/help/components/c-marketing-channels/c-faq.md#no-channel-identified)で説明されているように、残りのヒットを捕捉する「その他」**&#x200B;のチャネルを作成します。

## チャネルが識別されませんでした {#no-channel-identified}

When your rules do not capture data, or if rules are not configured correctly, the report displays the data in the [!UICONTROL No Channel Identified] row on the report. 例えば、内部トラフィックも識別する「*その他*」というルールセットを処理順序の最後に作成することができます。

![](assets/example_other.png)

This kind of rule serves as a catch-all to ensure that channel traffic always matches external traffic, and typically does not end up in **[!UICONTROL No Channel Identified]**. 内部トラフィックも識別してしまうルールを作成しないように注意してください。Setting the channel&#39;s value to **[!UICONTROL Referring Domain]** or to **[!UICONTROL Page URL]** are the most common, useful ways to create an effective Other rule.

> [!NOTE]一部のチャネルトラフィックは引き続き「チャネルが識別されませんでした」カテゴリーに分類される場合があります。例えば、訪問者がサイトを訪問してページをブックマークし、その訪問中にブックマークを使用してそのページに戻った場合がこれに該当します。このページは訪問者が最初に訪問したページではなく、参照ドメインが存在しないので、直接アクセスチャネルにもその他チャネルにも分類されません。

## 有料検索 {#paid-search}

有料検索とは、単語または語句が検索エンジンの検索結果ページに配置されるように料金を支払うことです。To match paid search detection rules, the marketing channel uses settings configured on the [!UICONTROL Paid Search Detection] page. ( **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Paid Search Detection]**). リンク先 URL はその検索エンジンの既存の有料検索検知ルールと一致します。

For the marketing channel rule, the [!UICONTROL Paid Search] settings are as follows:

![](assets/example_paid_search.png)

詳しくは、管理ヘルプの「[有料検索検知](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html)」を参照してください。

## 自然検索 {#natural-search}

自然検索は、Web 検索リストでの掲載順位に対して料金を支払わない場合に検索エンジンで決定される掲載位置から貴社の Web サイトを訪問者が見つけた場合に発生します。検索エンジンから貴社のサイトにリンクするときに使用されるリンク先 URL を制御できます。この URL によって、Analytics が自然検索かどうかを識別できます。

Analytics には自然検索の検出は用意されていません。有料検索検知を設定すると、検索リファラーが有料検索リファラーでなかった場合は、リファラーを自然検索リファラーにする必要があるとシステムで判断されます。自然検索の場合、リンク先 URL はその検索エンジンの既存の有料検索検知ルールに一致しません。

マーケティングチャネルルールでは、自然検索の設定は次のようになります。

![](assets/example_natural_search.png)

詳しくは、管理ヘルプの「[有料検索検知](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html)」を参照してください。

## アフィリエイト {#afilliates}

アフィリエイトのルールは、指定された一連の参照ドメインからの訪問者を識別します。このルールでは、追跡するアフィリエイトのドメインを次のように一覧表示します。

![](assets/example_affiliates.png)

## SNS {#social-networks}

このルールは、Facebook* などのソーシャルネットワークからの訪問者を識別します。以下のように設定できます。

![](assets/example_social.png)

## 表示 {#display}

このルールは、バナー広告から来た訪問者を識別します。これはリンク先 URL のクエリー文字列パラメーターによって識別されます（この場合   *`Ad_01`*.

![](assets/example_display.png)

## 内部からのアクセス {#internal}

このルールは、レポート スイートの内部 URL フィルターと一致するリファラーから派生する訪問者を識別します。

![](assets/example_internal.png)

## 電子メール {#email}

このルールを設定するには、電子メールキャンペーンのクエリー文字列パラメーターが必要です。この例では、パラメーターは     *`eml`*:

![](assets/example_email.png)

ルールにトラッキングコードが含まれている場合は、下図に示すように、それぞれの行に値を 1 つずつ入力します。

![](assets/tracking_code.png)

## 直接アクセス {#direct}

このルールは参照ドメインのない訪問者を識別します。このルールには、お気に入りリンクをクリックしたり、ブラウザーにリンクを貼り付けたりしてサイトに直接アクセスした訪問者が含まれます。

![](assets/example_direct.png)

