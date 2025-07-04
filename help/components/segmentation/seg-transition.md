---
description: レガシーセグメントの管理に関するよくある質問（FAQ）
title: レガシーセグメントに関するよくある質問
feature: Segmentation
exl-id: 316e2a2e-55d3-4c23-9985-9a6d90390e86
source-git-commit: 80e4a3ba4a5985563fcf02acf06997b4592261e4
workflow-type: tm+mt
source-wordcount: '1441'
ht-degree: 91%

---

# レガシーセグメントに関するよくある質問

この記事では、従来のセグメント（2014 年以前に作成されたセグメント）を管理するためのベストプラクティスに関するよくある質問に対する回答を示します。

## レガシーセグメントの管理 {#legacy}

+++ **既存のセグメントへの影響**

既存のセグメントは、引き続きこれまでと同様に機能します。既存のセグメントが適用されたレポートも、これまでと同様に適切に機能します。

以前の事前定義済みのおよびスイートセグメントのほとんどは、セグメントテンプレートとしてセグメントビルダーに移行されます。 セグメントテンプレートは、一般的な閲覧者を含むカスタムセグメントをすばやく作成するために部品として利用できます。セグメントテンプレートは、レポートに直接適用できませんが、カスタムセグメントには容易に保存できます。

セグメントビルダーでは、セグメントテンプレートに次のような特別なアイコンが表示されます。

![](assets/seg_templates.png)

+++

+++ **セグメントが適用された予定レポートへの影響**

配信レポートは、定義済みのセグメントと共に、これまでと同様に適切に実行されます。

セグメントを削除しても、そのセグメントが適用された配信レポートとダッシュボードは、これまでどおりに機能します。つまり、セグメントやダッシュボードは、削除されたセグメントを使い続けます。

同じ名前を持つセグメントを編集しても、配信レポートは更新されません。具体的な例を見てみましょう。次に示すように、同じ名前を持つ 2 つのセグメントを、別々のレポートスイートで使用しているとします。

![](assets/duplicate_seg_names.png)

このとき、mainprod レポートスイートのセグメントを参照するブックマークがあるとします。このセグメントは重複しているので、セグメントを削除します。その後も、このブックマークは引き続き、削除されたセグメントの定義を参照します。ここで maindev セグメントのセグメント定義に手を加え、カタリナ島とメキシコのティフアナを含めるように変更しても、このブックマークに適用されているセグメントは変更されません。このセグメントは古い定義を使用したままです。これを修正するには、新しい定義を参照するようにブックマークを更新します。ブックマーク、ダッシュボードまたは配信レポートで削除されたセグメントを使用しているかどうかが不明な場合は、残りのセグメントの名前を変更できます。ブックマークが残りのセグメントを使用しているかどうかがより明確になります。

+++

+++ **データウェアハウスセグメントへの影響**

既存のデータウェアハウスセグメントは、今後もデータウェアハウス内ですべて機能します。また、ほとんどのデータウェアハウスセグメントは、Analysis Workspace などの他のコンポーネントでも機能します。

新しい Data Warehouse セグメントは、セグメントビルダーとセグメントマネージャで作成または編集できます。セグメントビルダーの製品互換性メカニズムによって、セグメントがData Warehouseと互換性があるかどうかが自動的に判断されます。

+++

+++ **事前設定済みのセグメントへの影響**

* **直帰数**
* **モバイルデバイスからの訪問**
* **自然検索からの訪問**
* **有料検索からの訪問**
* **訪問者 ID cookie を使用した訪問**

これらのセグメントは、セグメントテンプレートとしてセグメントビルダーに移行されます。 既存のレポートにこのセグメントが適用されている場合でも、そのレポートは引き続き正しく動作します。

+++

+++ **Experience Cloud（スイート）セグメントへの影響：**

* 非購入者
* 購入者
* 初回訪問回数
* ソーシャルサイトからの訪問件数
* 10 分を超える訪問*
* 以前に 5 回以上の訪問履歴がある訪問*
* Facebook からの訪問件数*

これらのセグメントのほとんどは（アスタリスク * が付いているセグメントを除く）、セグメントテンプレートとしてセグメントビルダーに移行します。このほかに、新しいセグメントテンプレートがいくつか追加されています。

セグメントが適用された既存のレポートも、これまでと同様に適切に機能します。

+++

+++ **管理者セグメント（「グローバル」セグメントとも言う）への影響**

**管理**&#x200B;セグメントは、新しいセグメントインターフェイスに移行し、全員が共有するセグメントとして表示されます。

このセグメントの所有者は、ログイン企業の管理者ユーザー一覧に記載されているアカウントのうち、最も古くから存在する管理者に設定されます。ただし、管理者であれば誰でも、このセグメントの削除、編集および共有が可能です。

管理者がグローバルセグメントの作成および管理に使用していた Admin Console のセグメント管理インターフェイスは、利用できなくなりました。現在、管理者は新しいセグメントビルダーを使用して、セグメントを作成し、適切なグループ、個人またはすべてのユーザーとセグメントを共有します。

この変更されたロジックを使用する既存のセグメントも引き続き正しく機能しますが、それらのセグメントを保存するには、その前にセグメントを更新する必要があります。例えば、米国の州に「ニューヨーク」を含む既存のセグメントがある場合、このセグメントは正しく機能しますが、次にこのセグメントを編集するときには、列挙型と等号条件を使用するように更新する必要があります。

+++

+++ **同じ名前でありながら定義が異なるセグメントがある場合には、どうしたら良いでしょうか？**&#x200B;セグメントが複数のレポートスイートで動作するようになったことから、同じ名前のセグメントが複数存在する結果になることがあります。そのような場合には、以下のいずれかを推奨しています。

* 同じ名前でありながら定義が異なるセグメントの名前を変更します。
* 不要なセグメントを削除します。

+++

+++ **セグメントのクリーンアップに関して、どんなことが推奨されていますか？**

* すべてのセグメントに「移行前」などのタグを付けます。
* 自分が所有しているセグメントを確認します。
* セグメントを適切なセグメントライブラリに追加します。
* 正規のセグメントを承認します。
* [ベストプラクティス](/help/components/segmentation/segmentation-workflow/seg-workflow.md)に従ってセグメントにタグを設定します。

+++

### 移行に関するヒント

次のヒントは、一般的なディメンションを移行するのに役立ちます。

* 地域 - 市／地域／国 - 部分一致を使用するのではなく、特定の市町村、地域または国を検索して選択します。
* ブラウザー - ブラウザタイプディメンションを使用して、すべてのブラウザーを Google Chrome などのタイプによって取得します。
* オペレーティングシステム - OS の種類ディメンションを使用して、すべてのオペレーティングシステムを Microsoft Windows などの種類によって取得します。
* 「新しいディメンションと名前が変更されたディメンション」を参照してください（以下を参照）。

## 新しいディメンションと名前が変更されたディメンション {#renamed}

セグメントビルダーで名前が変更されたディメンションのリストを次の表に示します。

| 新しいディメンション名 | 以前の名前 | メモ |
|--- |--- |--- |
| オペレーティングシステムの種類 | 新規 | 2015 年春に追加されました。 |
| ブラウザーの幅 - グループ | ブラウザーの幅 | このディメンションは、すべてのインターフェイスと互換性があり、特定の整数値ではなく、範囲の列挙型リストに分割されます。特定の値をセグメント化する必要がある場合は、このディメンションの詳細バージョンを Data Warehouse セグメントで使用します。 |
| ブラウザーの高さ - グループ | ブラウザーの高さ | このディメンションは、すべてのインターフェイスと互換性があり、特定の整数値ではなく、範囲の列挙型リストに分割されます。特定の値をセグメント化する必要がある場合は、このディメンションの詳細バージョンを Data Warehouse セグメントで使用します。 |
| ブラウザーの幅 - 詳細 | ブラウザーの幅 | これは名前が変更され、現在は Data Warehouse とのみ互換性があります。すべてのインターフェイスと互換性があるセグメントを定義するには、列挙型の「ブラウザーの幅 - グループ」を使用します。 |
| ブラウザーの高さ - 詳細 | ブラウザーの高さ | これは名前が変更され、現在は Data Warehouse とのみ互換性があります。すべてのインターフェイスと互換性があるセグメントを定義するには、列挙型の「ブラウザーの高さ - グループ」を使用します。 |
| cookie サポート | Cookie | - |
| 色深度 | 画面の色設定 | - |
| - | &quot;アプリ - *&quot; | &quot;アプリ -&quot; プリフィックスは、多数のディメンションタイプから削除されました。一般に、モバイルアプリデータは、Web データを含まないレポートスイートに収集されるので、これらのプリフィックスは不要でした。 |
| オリジナルの入口ページ | オリジナルの入口ページ | - |
| Java 有効 | Java | - |
| モバイルのブラウザー URL 最大長 | モバイルブラウザー URL の長さ | - |
| モバイルデコレーションメール | モバイルデコレーションメールのサポート | - |
| モバイルデバイス | モバイルデバイス名 | - |
| モバイルのブックマーク最大長 | モバイル ブックマーク URL の最大長 | - |
| モバイルの電子メール最大長 | モバイル メール URL の最大長 | - |
| モバイルオペレーティングシステム（非推奨） | モバイル OS | オペレーティングシステムディメンションを使用し、代わりに、モバイルデバイスセグメントからの訪問を適用します。 |
| モバイルプッシュトゥトーク | モバイル PTT | - |
| 調査ビュー | 調査表示回数合計 | - |
| 調査の回答 | 調査回答数合計 | - |
| 訪問の深さ | パスの長さ | - |
| 郵便番号 | 郵便番号 | - |

{style="table-layout:auto"}

## 既知の値を持つ文字列ベースのディメンションへの変更 {#string-based-dims}

既知の値のセットを持つ文字列ベースのディメンションは列挙型に変更されました。これらのディメンションを使用してセグメントを作成すると、リストにすべての既知の値が事前に設定されます。演算子は等号のみがサポートされます。したがって、必要な値をすばやく正確にセグメント化でき、制限の緩いマッチングによって意図しない値が選択されることはありません。

次のディメンションが列挙型リストに変更されました。

| ディメンション名 | ディメンション名 | ディメンション名 |
| --- | --- | --- |
| モバイルの製造元 | モバイルの電子メールの長さ | 色深度 |
| モバイルの画面のサイズ | モバイルデバイス番号 | 画面の解像度 |
| モバイルの画面の高さ | モバイルプッシュトゥトーク | プラグイン |
| モバイルの Cookie サポート | モバイルデコレーションメール | オペレーティングシステム |
| モバイルの画像サポート | モバイル情報サービス | リファラータイプ |
| モバイルの画面の色 | モバイルデバイスタイプ | 検索エンジン |
| モバイルのオーディオサポート | ブラウザータイプ | 都道府県 |
| モバイルのビデオサポート | ブラウザー | 地域 - 国 |
| モバイル DRM | 接続タイプ | 地域 - 地域 |
| モバイルインターネットプロトコル | 携帯電話会社 | 地域 - 市 |
| モバイル OS | cookie | 地域 - DMA |
| モバイル Java VM | 顧客の忠誠度 | 永続的な Cookie |
| モバイルのブックマークの長さ | Java 有効 | 有料検索 |
| モバイルの URL の長さ | 言語 |  |

## 既知の値を持つ整数ベースのディメンションへの変更 {#integer-based-dims}

既知の値のセットを持つ整数値ベースのディメンションは列挙型の範囲に分割されたので、特定の範囲に対してセグメントをすばやく定義できます。これらの列挙型リストには、ディメンション名の後に「- グループ」が付きます。以前のセグメントビルダーインターフェイスと新しいセグメントビルダーインターフェイスを使用して、これらのディメンションをセグメント化する方法を次のスクリーンに示します。

![](assets/seg_browser_dimension.png)

より小さい、より大きい、および類似の演算子は、現在、Data Warehouse セグメントとのみ互換性があります。すべてのレポートインターフェイスと互換性を持つことを意図したセグメントでは、指標の「グループ」バージョンと等号演算子を使用する必要があります。
