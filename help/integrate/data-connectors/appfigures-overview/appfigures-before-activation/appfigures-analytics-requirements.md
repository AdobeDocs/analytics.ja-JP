---
description: 'このData Connectors統合に関する情報を、Adobe Analyticsと同様に確認します '
seo-description: 'このData Connectors統合に関する情報を、Adobe Analyticsと同様に確認します '
seo-title: Adobe Analyticsの要件
title: Adobe Analyticsの要件
uuid: cc7e3b0e-3e4b-4aa7-899f- d6b8f82227dd
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Adobe Analytics Requirements{#adobe-analytics-requirements}

Adobe Analyticsに関するこのdata connectors統合に関する次の情報を確認します。

* **レポートスイート固有:** この統合はレポートスイート固有であることをお勧めします。統合をアクティブ化する前に、目的のレポートスイートが選択されており、レポートスイートにデータが含まれていることを確認してください。
* **利用可能なAnalytics変数および設定済みの変数:** この統合には、10個のカスタムイベントと1個のカスタムeVarが必要です。[Analytics統合変数](../../appfigures-overview/appfigures-before-activation/appfigures-variables.md#concept-6c8a359719fd4794a42f5f6fb118f8b2)を参照してください。

* **レポートスイートがライブデータで初期化されました:** この統合用に新しいレポートスイートを作成する場合は、「ライブ」追跡を使用して（少なくとも1つのヒット）データを受信する必要があります（ [Adobe Analyticsの要件](../../appfigures-overview/appfigures-before-activation/appfigures-analytics-requirements.md#concept-3bf6a42b3b2f46cf84f929b91a1ad65c)の説明）。「ライブ」データが記録されていない場合、レポートスイートは統合App Storeデータを受信する準備ができません。

* **App Storeとの既存の統合:** この統合は、13ヶ月分のデータを埋めます。以前のApp Storeデータプロバイダーと重複しないようにするには、appFiguresの担当者にお問い合わせください。データを受信した最終日付を伝えます。appFiguresは、それに応じてバックフィル期間を調整します。

