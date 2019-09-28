---
description: タイムスタンプのあるデータとないデータの両方を組み合わせて 1 つのレポートスイートにします。
seo-description: タイムスタンプのあるデータとないデータの両方を組み合わせて 1 つのレポートスイートにします。
seo-title: タイムスタンプオプション
solution: Analytics
title: タイムスタンプオプション
topic: 管理ツール
uuid: 0fa63658-1cc2-4adc-8d51-a0662d0aa941
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# タイムスタンプオプション

タイムスタンプのあるデータとないデータの両方を組み合わせて 1 つのレポートスイートにします。

タイムスタンプオプションを使用すると、次のことができます。

* タイムスタンプのデータが存在するイメージリクエストと存在しないイメージリクエストを 1 つのグローバルレポートスイートで計測できます。
* モバイルアプリから Web 用のレポートスイートにタイムスタンプ付きのデータを送信できます。
* 公開済みアプリをアップデートし、途中からオフライン計測を開始する場合でも、既存のレポートスイートを引き続き利用できるようになりました。

レポートスイートでタイムスタンプを使用する際のベストプラクティスについては、[タイムスタンプオプションの使用](/help/implement/js-implementation/timestamps-overview.md)を参照してください。

>[!IMPORTANT]
>
>If you are using Timestamps Optional, then do not set [s.visitorID](https://marketing.adobe.com/resources/help/en_US/sc/implement/visid_custom.html) on data that is already timestamped. これにより、データが破壊され、時間の計算（滞在時間値など）、属性（eVar の持続性）、訪問回数／訪問のカウントおよびパスレポートに悪影響を与える可能性があります。

>[!NOTE]
>
>タイムスタンプが有効なセッションデータは、最大 92 日間保持されます。つまり、前回のヒット（ヒット時間）から30分以内でない追加のヒットが同じ訪問/セッションに含まれる間、訪問/セッションは92日間「開いたまま」となります。 Any "old" hits that are received out of order will produce "unknown" results, since a number of factors (segmentation, allocation, expiration, etc.) これらのヒットがレポートに含まれるかどうかに影響を与えます。

## 新しいレポートスイート {#section_095A7CFBD280494593B9BEC1592B73A6}

* テンプレートから作成された場合、新しいレポートスイートでは、デフォルトでタイムスタンプオプションが設定されます。

   （**管理者／レポートスイート／新規作成／レポートスイート**&#x200B;で、テンプレートから新しいレポートスイートを作成できます。）
* 既存のレポートスイートからコピーした場合、新しいレポートスイートは、元のレポートスイートから次のようなタイムスタンプ設定を継承します。

   * **タイムスタンプを使用できない**（s.visitorID の設定はサポートされている）
   * **タイムスタンプが必要**（s.visitorID の設定はサポートされていない）
   * **タイムスタンプオプション**（s.visitorID の設定はサポートされているが、タイムスタンプ付きのヒットではサポートされない）

## 既存のレポートスイートをタイムスタンプオプションに変更するには {#section_40BCD3B4639241DEA716F7640ED33E72}

1. **管理者／レポートスイート／設定を編集／一般／タイムスタンプの設定**&#x200B;に移動します。
1. 「**選択されたレポートスイートをタイムスタンプオプションに変換**」ボックスを選択します。

   これで、レポートスイートがタイムスタンプオプションに変更されます。

>[!NOTE]
>
>If a report suite was set to **Timestamps Optional**, to change this to any other setting, please contact Adobe Client Care.

