---
description: 成功イベントとは、追跡できるアクションです。成功イベントはお客様によって定義されます。例えば、訪問者があるアイテムを購入した場合、その購入イベントは成功イベントと見なすことができます。
keywords: イベント
title: 成功イベントの概要
feature: Event
exl-id: d52a691a-8124-4601-932f-d6d2d0a7842b
source-git-commit: 84a4d38a65769f028bac4aa5817cb4002c4b1f97
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 100%

---

# 成功イベントの概要

成功イベント（コンバージョンイベントまたはカスタムイベントとも呼ばれます）は、トラッキングが可能なアクションです。成功イベントはお客様によって定義されます。例えば、訪問者があるアイテムを購入した場合、その購入イベントは成功イベントと見なすことができます。

以下は、このトピックの概要に関するビデオです。

>[!VIDEO](https://video.tv.adobe.com/v/28764/?quality=12)

レポートスイート設定の成功イベントページにアクセスします。

1. Adobe ID の資格情報を使用して [experiencecloud.adobe.com](https://experiencecloud.adobe.com) にログインします。
2. 上部の 9 グリッドボタンをクリックし、「[!UICONTROL Analytics]」をクリックします。
3. [!UICONTROL 管理者]／[!UICONTROL レポートスイート] に移動します。
4. 目的のレポートスイートを選択し、 [!UICONTROL 設定を編集]／[!UICONTROL コンバージョン]／[!UICONTROL 成功イベント] に移動します。
5. 目的のイベントを見つけ、「[!UICONTROL 個別イベントの記録]」ドロップダウンを「[!UICONTROL 訪問ごとに 1 回記録する]」または「[!UICONTROL イベント ID を使用する]」に変更します。

Web サイトのタイプに応じて、様々な種類の成功イベントがあります。次にいくつか例を示します。

* **小売**：商品ビュー、チェックアウト、購入
* **メディア**：購読、コンテンツ申し込み、ページビュー、ビデオビュー
* **ファイナンス**：申込書の送信、ログイン、セルフサービスツールの使用
* **旅行**：予約（購入）、内部キャンペーン（クリックスルー）、検索（旅行の価格決定）
* **電気通信**：購入、リード、セルフサービスツールの使用
* **ハイテク**：ホワイトペーパーのダウンロード、RFP、フォーム入力、サポート要求
* **自動車**：リードの送信、見積の要求、パンフレットのダウンロード

[s.events](https://experienceleague.adobe.com/docs/analytics/implementation/vars/page-vars/events/event-serialization.html?lang=ja) 変数は、成功イベントを定義するためのものです。

## 成功イベントページ - 説明 {#section_681ECEC981694CABBDBF00E18165B447}

**[!UICONTROL Analytics]**／**[!UICONTROL 管理者]**／**[!UICONTROL レポートスイート]**／**[!UICONTROL 設定の編集]**／**[!UICONTROL コンバージョン]**／**[!UICONTROL 成功イベント]**

成功イベントページではサイトで使用するイベント変数を設定します。成功イベントは 1,000 件まで追加できます。イベント 81 - 1,000 は、H22 コード以上でのみ動作します。

| 要素 | 説明 |
|--- |--- |
| イベント | イベントの元の名前 |
| 名前 | サイトで使用する成功イベントに意味のある名前を付けます。例えば、イベント 1 を登録の追跡に使用する場合、イベント 1 がすべてのコンバージョンレポートで「登録」指標として表示されるように名前を変更します。 |
| タイプ | 選択されたタイプは、イベントがカウンター（標準）、数値または通貨イベントのいずれであるかを決定します。数値イベントおよび通貨イベントでは、1 つ以上の指標を増分できます。カウンターイベントは経時的にイベントを記録し、通貨イベントは税金や送料など小数点のある数字を記録します。通貨イベントに渡された値は、受け取った段階でそのページの通貨からレポートスイートのベース通貨に変換されます。通貨イベントの詳細については、アドビの担当者にお問い合わせください。数値イベントは、ある購入で使用されるクーポンの数など、通貨以外の数値を報告するために使用します。通貨イベントは、税金と送料の追跡に使用します。データソースの標準タイプで使用されるイベントは、数値イベントまたは通貨イベントでなければなりません。 |
| 極性 | 指標の極性によって、特定のカスタムイベント（指標）が上昇する場合、Adobe Analytics でそれを良いと見なすか悪いと見なすかを指定することができます。Adobe Analytics で、様々な指標に方向指示器（矢印）を表示して、コンテキスト（例えば、前週との比較）を理解できるようになります。例：前週比で「不具合の報告」が上昇する場合、Adobe Analytics はそれを良いと見なすべきでしょうか、それとも悪いと見なすべきでしょうか。電子メール登録の増加は、おそらく良いでしょう。しかし、フォーム送信エラーの増加は、おそらく悪いでしょう。Analysis Workspace では、フリーフォームテーブル条件付き書式、概要変更の視覚化、およびマップ視覚化の正／負のカラースキームに極性が適用されます。 |
| 説明 | イベントの目的と使用状況に関する簡単な説明です。 |
| 個別イベントの記録 | **訪問ごとに 1 回記録する**：特定のイベントを訪問者のセッションに結び付けます。同じ訪問内の特定のイベントに対する、以降のカウントは無視されます。この種のイベントのシリアル化では、実装の変更は必要ありません。<br>**イベント ID を使用**：渡されたイベントをカスタム ID に結び付けます。イベント ID が同じ特定のイベントに対する以降のカウントは無視されます。このタイプのイベントシリアル化では、値の重複を除外するために、ヒットのカスタム ID が必要です。実装ユーザーガイドの「[イベント ID のシリアル化](/help/implement/vars/page-vars/events/event-serialization.md)」を参照してください。 |
| パーティシペーション | 訪問のすべてのディメンション項目にフルアトリビューションクレジットを与えます。 |
| 警告（通貨イベント） | イベントタイプを通貨イベントに変更したり、通貨イベントから変更したりするときには、履歴データがレポートで利用できなくなることを示すメッセージが表示されます。イベントタイプが異なれば使用するデータテーブルも異なるので、異なるイベントタイプを同時に使用することはできません。履歴データによっては、イベントタイプを元に戻したときに復元できることがあります。ただし、最初に変更してから収集されたデータは利用できません。イベントタイプを変更するときには、注意が必要です。 |