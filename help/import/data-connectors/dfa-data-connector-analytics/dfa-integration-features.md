---
description: 'アクティブ化すると、Data Connectors DFA 統合によって、Adobe Analytics レポート用の次の指標が提供されます '
keywords: DFA
title: 統合の機能
topic: Data connectors
uuid: 4ad8e6e8-3449-498a-8596-37c0ac1657cd
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# 統合の機能 {#integration-features}

アクティブ化すると、Data Connectors DFA 統合によって、Adobe Analytics レポート用の次の指標が提供されます。

* 表示スルー
* DFAクリック数
* インプレッション
* （オプション）DFAコストデータ
* （オプション）DFAクエリエラー、タイムアウト

>[!NOTE]この統合では、クリックトラッカー（以前のクリックコマンド）はサポートされません。クリックトラッカーは、テキストリンク、電子メールメッセージ内のリンク、またはWebサイト上でハードコードされた他の要素のクリック数を記録するために使用されます。

Data Connectors DFA統合は、DFAから返されたデータからDFAトラッキングコードを自動的に構築します。 これらのトラッキングコードは、広告とその関連するプレースメントおよびクリエイティブを一意に識別するために構築されます。 統合のバージョンに応じたトラッキングコードの構造の概要を次に示します。 バージョン1.5は次のようになります。

![](assets/DFA_id_struct1_5.png)

バージョン2.0は次のようになります。

![](assets/DFA_id_struct2.png)

これらのIDは、正しい分類と指標を関連付けるために、GenesisとDFAの間の共有キーとして機能します。

| サイト ID | 広告がホストされたサードパーティサイト。 サイト名の分類は、このサイトIDを説明する名前を提供します。 |
|---|---|
| 広告 ID | ユーザーに配信されるコマーシャルのID。 広告名の分類には、DFAシステムで組織が定義した広告の名前が含まれます。 例：`Hybrid Coup Textlink - Build`。 |
| プレースメント ID | 広告スペースを購入したWebサイト、Webサイトの一部、またはWebサイトのグループのDFAアカウント内の表現。 |
| クリエイティブ ID | 画像、Flash SWFまたは訪問者に表示する他のリソース。 クリエイティブ名の分類には、DFAインターフェイスでこのクリエイティブに指定した名前が含まれます。 |

他の2つの分類(配信ツール(DoubleClick for Advertisers)とチャネル（バナー広告）は、DFAキャンペーンに対して同じ値を持ち、DFAインポートされたデータを区別するのに役立ちます。

## SearchCenterの重複除外 {#section-f809b3bb5e5142aa8ff89bcd5f0d0e49}

DFA 統合は、Adobe SearchCenter に対応しています。Data Connectors ウィザードで SearchCenter 重複除外を有効にすると、検索による訪問者は DFA の Floodlight サーバーからデータを取得しなくなります。DFA によって *`s.campaign`* が入力されないので、SearchCenter によってデータを生成できるようになります。また、DFAとSearchCenterでは、各製品の変数に重複除外の値が設定されるようになりました。

次のリストでは、SearchCenterの重複除外が有効な場合に有効になるロジックの概要を説明します。

ウィザード **[!UICONTROL DFA]** で「>」 **[!UICONTROL SearchCenter deduplication]** が選択されている場合：

* DFA クリックスルーの場合、統合は、設定した SCM eVar に文字列「DFA Clickthrough」を設定します。
* DFA ビュースルーの場合、統合は、SCM eVar に文字列「DFA Viewthrough」を設定します。

ウィザード **[!UICONTROL SearchCenter]** で「>」 **[!UICONTROL DFA deduplication]** が選択されている場合：

* DFA ビュースルーの場合、統合は、SCM eVar に文字列「DFA Viewthrough」を設定します。

>[!NOTE]SearchCenter／DFA 重複除外が有効になっており、SearchCenter クエリー文字列パラメーターが設定されている場合、DFA 処理では訪問は考慮されません。つまり、SearchCenter クエリー文字列パラメーターは、DFA クリックスルーパラメーターとは異なる必要があり、表示広告に SearchCenter クエリー文字列パラメーターが設定されないようにする必要があります。

