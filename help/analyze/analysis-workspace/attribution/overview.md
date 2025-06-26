---
title: アトリビューションの概要
description: 成功イベントのクレジットを複数のディメンション項目に関連付ける概念。
feature: Attribution
role: User, Admin
exl-id: 47a3523b-d9eb-4272-84b8-090b921cba13
source-git-commit: 8f7c6a0d1477b599b05aeb7b74c4ee96531d294d
workflow-type: tm+mt
source-wordcount: '486'
ht-degree: 89%

---

# アトリビューションの概要

アトリビューションを使用すると、分析者は、成功イベントのクレジットをディメンション項目がどのように取得するかをカスタマイズできます。次に例を示します。

1. サイトの訪問者が、いずれかの商品ページへの有料検索リンクをクリックします。商品を買い物かごに追加しますが、購入はしません。
2. 次の日に、訪問者は友達の 1 人からのソーシャルメディアの投稿を見てリンクをクリックし、購入を完了します。

一部のレポートでは、注文を有料検索に関連付けることが望まれるかもしれません。他のレポートでは、注文を「ソーシャル」に関連付けることが望まれるかもしれません。アトリビューションを使用すると、このレポートの側面を制御できます。Adobe Analytics Ultimate、Prime、Select、Foundation ですべての組織で利用できます。アドビとの契約のタイプが不明な場合は、組織のアドビのアカウントチームにお問い合わせください。

## アトリビューションの値

特定のカスタマージャーニーは、線形ではなく、予測不可能な場合も多くあります。各顧客は、それぞれのペースで進みます。多くの場合、ダブルバック、停止、再起動、または他の非線形動作に関与します。このような生物的なアクションにより、カスタマージャーニー全体を通したマーケティング活動の影響を把握することが難しくなっています。また、複数のチャネルのデータを結び付ける作業の妨げにもなります。

<!--
![Attribution problem](assets/attribution_iq_problem.png)
-->

Adobe Analytics を使用すると、以下が可能になるので、アトリビューションを強化できます。

* 有料メディアに勝るアトリビューションの定義：マーケティングキャンペーンだけでなくあらゆるディメンション、指標、チャネル、イベントをモデルに適用できます（例：内部検索）。
* 無制限のアトリビューションモデル比較の利用：必要な数のモデルを動的に比較できます。
* 実装の変更の回避：レポート時間処理とコンテキスト対応セッションで、カスタマージャーニーのコンテキストを実行時間に組み込んで適用できます。
* アトリビューションシナリオに最適なセッションの作成。
* アトリビューションのセグメント別分類：すべての重要なセグメントにわたってマーケティングチャネルのパフォーマンスを容易に比較できます（例：新規顧客とリピート顧客、製品 X と製品 Y、忠誠度または CLV）。
* チャネルのクロスオーバー分析およびマルチタッチ分析の調査：ベン図やヒストグラムを使用でき、アトリビューション結果のトレンドを追跡できます。
* 主要なマーケティングシーケンスの視覚的分析：コンバージョンにつながったパスをマルチノードのフローおよびフォールアウトビジュアライゼーションで視覚的に調査できます。
* 計算指標の構築：任意の数のアトリビューション割り当て方法を使用できます。

## 機能

アトリビューションは、次の機能で構成されます。

* [アトリビューションパネル](../c-panels/attribution.md)：任意のディメンションと指標を使用して、様々なアトリビューションモデルとすばやく比較できます。
* [指標へのアトリビューションの適用](../visualizations/freeform-table/column-row-settings/column-settings.md)：プロジェクト内の任意の指標にデフォルト以外のアトリビューションを使用します。
* [分類へのアトリビューションの適用](../components/dimensions/t-breakdown-fa.md)：分類にデフォルト以外のアトリビューションを使用します。
* [アトリビューションモデルの比較](../components/apply-create-metrics.md)：指標ごとに異なるアトリビューションモデルがどのように比較されるかをすばやく確認できます。

## ビデオ


>[!BEGINSHADEBOX]

デモビデオについては、![ フリーフォームテーブルの VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg)[ アトリビューション ](https://video.tv.adobe.com/v/23136?quality=12&learn=on){target="_blank"} を参照してください。

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

デモビデオについては、![ 計算指標での VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg)[ アトリビューション ](https://video.tv.adobe.com/v/23140?quality=12&learn=on){target="_blank"} を参照してください。

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg)[ アトリビューションパネルの使用 ](https://video.tv.adobe.com/v/23139?quality=12&learn=on){target="_blank"} を参照してください。

>[!ENDSHADEBOX]


>[!BEGINSHADEBOX]

デモビデオについては、![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg)[ アトリビューションモデルの並列比較の追加 ](https://video.tv.adobe.com/v/23651?quality=12&learn=on){target="_blank"} を参照してください。

>[!ENDSHADEBOX]


## アトリビューションをサポートしないAdobe Analytics ツール

Analytics 2.0 API をサポートしないすべてのツール（Report Builder など）は、アトリビューションをサポートしません。
