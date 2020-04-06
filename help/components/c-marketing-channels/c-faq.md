---
description: マーケティングチャネルに対して設定可能な様々なルールを入力するためのベストプラクティスと例をご確認ください。
title: マーケティングチャネルに関するFAQと例
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# マーケティングチャネルに関するFAQと例

See [Create Marketing Channel Processing Rules](/help/components/c-marketing-channels/c-rules.md) for definitions of fields displayed on the [!UICONTROL Marketing Channel Processing Rules] page.

## よくある質問 {#faq}

マーケティングチャネルの処理ルールの実装は、トラッキングコードによって異なる場合があります。 求める結果を与えるルールを設定するには、問題を解決するための創造的な思考が必要になる場合があります。

**質問**:トラッキングコードがパターンに従っておらず、アフィリエイトのチャネル用に指定する必要があるコードが何千もあります。

* 削除のプロセスを使用します。 電子メールチャネルとアフィリエイトチャネルに同一のクエリー文字列パラメーターを使用しているとき、電子メールのトラッキングコードが少数なら、電子メールを定義するルールセットで電子メールトラッキングコードを指定することができます。次に、他のすべてのトラッキングコードを *`affiliates.`*
* 電子メールシステムで、ランディングページのすべての URL に *`&ch=eml`* などのクエリー文字列パラメーターを追加します。ch クエリパラメーターが *`eml`* と等しいかどうかを検出するルールセットを作成します。*`eml`* が含まれない場合はアフィリエイトです。

**質問**：参照ドメインに予想より多くのデータが含まれています。

* 参照ドメインが処理ルールのドメインの値を超過する可能性があります。リスト 処理順序が重要なので、下位の方（または最下位）に配置してください。

**質問**：クエリー文字列パラメーターに一致するルールを作成しましたが、うまく機能しません。

* クエリー文字列パラメーターのフィールドでパラメーター名（通常は英数字の値）が指定されていることを確認してください。また、次の電子メールルールの例に示すように、演算子の後にパラメーター値が指定されていることを確認してください。

   ![](assets/example_email.png)

**質問**:ラストタッチトラフィックの属性がすべて内部ドメインになっているのはなぜですか。

* 内部トラフィックに一致するルールがある。 これらのルールは、最初の訪問だけでなく、訪問者がサイトで行うすべてのヒットに対して処理されることに注意してください。 If you have a rule like *`Page URL exists`* without other criteria, that channel is matched on each successive hit on your site, because a page URL always exists.

**質問**:レポートに「識別されませんでした」と表示されるチャネルをデバッグする方法を教えてください。

* ルールは順番に処理されます。 一致する特定の条件がない場合、ヒットは次の3つのカテゴリのいずれかに分類されます。

1. リファラーなし（直接訪問）。

2. 内部リファラー、訪問の最初のページ。

3. ページの処理異常。

この3つの可能性に対するチャネルがあることを確認します。 例えば、次のようなルールを作成します。

1. **[!UICONTROL Referrer]** そして **[!UICONTROL Does Not Exist]** と **[!UICONTROL Is First Page of Visit]**&#x200B;を （[直接](/help/components/c-marketing-channels/c-faq.md)を参照）

2. **[!UICONTROL Referrer Matches Internal URL Filters]** と **[!UICONTROL Is First page of Visit]**.（[内部](/help/components/c-marketing-channels/c-faq.md)を参照）。

3. **[!UICONTROL Referrer]** そして **[!UICONTROL Exists]** と **[!UICONTROL Referrer Does Not Match Internal URL Filters]**&#x200B;を

最後に、「[チャネルが識別されませんでした](/help/components/c-marketing-channels/c-faq.md#no-channel-identified)」で説明されているように、残りのヒットを捕捉する「*その他*」のチャネルを作成します。

## No Channel Identified {#no-channel-identified}

ルールでデータが取り込まれない場合や、ルールが正しく設定されていない場合は、レポートの行にデータが [!UICONTROL No Channel Identified] 表示されます。 例えば、内部トラフィックも識別する「*その他*」というルールセットを処理順序の最後に作成することができます。

![](assets/example_other.png)

This kind of rule serves as a catch-all to ensure that channel traffic always matches external traffic, and typically does not end up in **[!UICONTROL No Channel Identified]**. 内部トラフィックも識別してしまうルールを作成しないように注意してください。Setting the channel&#39;s value to **[!UICONTROL Referring Domain]** or to **[!UICONTROL Page URL]** are the most common, useful ways to create an effective Other rule.

>[!NOTE]一部のチャネルトラフィックは引き続き「チャネルが識別されませんでした」カテゴリーに分類される場合があります。例：訪問者がサイトに来訪し、ページをブックマークし、同じ訪問でそのブックマークを介してページに戻ります。 これは訪問の最初のページではないので、参照チャネルがないので、直接ドメインでも他のチャネルでも表示されません。

## 有料検索 {#paid-search}

有料検索とは、検索エンジンに対して検索結果の配置に支払う単語またはフレーズのことです。 有料検索の検出ルールと一致させるため、マーケティングチャネルはページで設定された設定を使用 [!UICONTROL Paid Search Detection] します。 ( **[!UICONTROL Admin]** > **[!UICONTROL Report Suites]** > **[!UICONTROL Edit Settings]** > **[!UICONTROL General]** > **[!UICONTROL Paid Search Detection]**). リンク先URLは、その検索エンジンの既存の有料検索検知ルールと一致します。

マーケティングチャネルルールの [!UICONTROL Paid Search] 設定は次のとおりです。

![](assets/example_paid_search.png)

詳しくは [、管理ヘルプの「有料検索検知](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) 」を参照してください。

## 自然検索 {#natural-search}

自然検索は、訪問者がウェブ検索で貴社のウェブサイトを見つけたときに発生します。ウェブ検索では、貴社が掲載順位に対して料金を支払わないで検索エンジンにランク付けされています。 検索エンジンがサイトにリンクする際に使用するリンク先URLを制御できます。 このURLを使用すると、Analyticsで自然検索かどうかを識別できます。

Analyticsには自然検索の検出はありません。 有料検索検知を設定すると、検索転送者が有料検索転送者でない場合は、自然検索転送者である必要があることが分かります。 自然検索の場合、リンク先URLがその検索エンジンの既存の有料検索検知ルールと一致しません。

マーケティングチャネルルールの自然検索の設定は次のとおりです。

![](assets/example_natural_search.png)

詳しく [は、管理ヘルプの](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/paid-search-detection/paid-search-detection.html) 「有料検索検知」を参照してください。

## アフィリエイト {#afilliates}

アフィリエイトルールは、指定した参照訪問者のセットから派生するドメインを識別します。 ルールでは、次のように、追跡するアフィリエイトのリストを選択します。

![](assets/example_affiliates.png)

## SNS {#social-networks}

このルールは、Facebook*などのソーシャル訪問者から派生するネットワークを識別します。 設定は次のとおりです。

![](assets/example_social.png)

## 表示 {#display}

このルールは、バナー広告から来た訪問者を識別します。これはリンク先 URL のクエリー文字列パラメーターによって識別されます（この場合は&#x200B;*`Ad_01`*）。

![](assets/example_display.png)

## 内部からのアクセス {#internal}

このルールは、レポート スイートの内部 URL フィルターと一致するリファラーから派生する訪問者を識別します。

![](assets/example_internal.png)

## 電子メール {#email}

このルールを設定するには、電子メールキャンペーンのクエリー文字列パラメーターが必要です。この例では、パラメーターは     *`eml`*:

![](assets/example_email.png)

ルールにトラッキングコードが含まれる場合は、次に示すように、1行に1つの値を入力します。

![](assets/tracking_code.png)

## 直接 {#direct}

このルールは、参照訪問者を持たないドメインを識別します。 このルールには、お気に入りリンクから直接サイトにアクセスした訪問者や、ブラウザにリンクを貼り付けた訪問者が含まれます。

![](assets/example_direct.png)

